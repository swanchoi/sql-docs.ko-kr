---
title: GetReparentedValue(데이터베이스 엔진) | Microsoft Docs
ms.custom: ''
ms.date: 07/22/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- Reparent_TSQL
- Reparent
dev_langs:
- TSQL
helpviewer_keywords:
- Reparent [Database Engine]
ms.assetid: f47f8e25-08ef-498b-84f4-a317aca1f358
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 4bca90e100baf2a7509636966ee1391645827bb9
ms.sourcegitcommit: b3d84abfa4e2922951430772c9f86dce450e4ed1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56662787"
---
# <a name="getreparentedvalue-database-engine"></a>GetReparentedValue(데이터베이스 엔진)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

루트에서 _newRoot_까지의 경로 다음에 _oldRoot_에서 시작되는 경로가 오는 노드를 반환합니다.
  
## <a name="syntax"></a>구문  
  
```sql
-- Transact-SQL syntax  
node. GetReparentedValue ( oldRoot, newRoot )  
```  
  
```sql
-- CLR syntax  
SqlHierarchyId GetReparentedValue ( SqlHierarchyId oldRoot , SqlHierarchyId newRoot )  
```  
  
## <a name="arguments"></a>인수  
_oldRoot_  
수정할 계층 구조의 수준을 나타내는 노드인 **hierarchyid**입니다.
  
_newRoot_  
**hierarchyid**는 노드를 나타냅니다. 현재 노드의 _oldRoot_ 섹션을 바꿔서 노드를 이동합니다.
  
## <a name="return-types"></a>반환 형식  
**SQL Server 반환 형식: hierarchyid**
  
**CLR 반환 형식: SqlHierarchyId**
  
## <a name="remarks"></a>Remarks  
_oldRoot_에서 _newRoot_로 노드를 이동하여 트리를 수정하는 데 사용됩니다. GetReparentedValue는 계층 구조에서 계층 구조 노드를 새 위치로 이동하는 데 사용됩니다. **hierarchyid** 데이터 형식은 계층 구조를 나타내지만 적용하지는 않습니다. 사용자는 hierarchyid가 새 위치에 대해 적절히 구성되어 있는지 확인해야 합니다. **hierarchyid** 데이터 형식의 고유한 인덱스는 중복 항목을 방지하는 데 도움이 될 수 있습니다. 전체 하위 트리를 이동하는 예는 [계층적 데이터&#40;SQL Server&#41;](../../relational-databases/hierarchical-data-sql-server.md)를 참조하세요.
  
## <a name="examples"></a>예  
  
### <a name="a-comparing-two-node-locations"></a>1. 두 노드 위치 비교  
다음 예에서는 노드의 현재 hierarchyid를 보여 줍니다. 또한 **@NewParent** 노드의 하위 항목이 되도록 노드를 이동하는 경우 노드의 **hierarchyid**가 어떻게 달라지는지 보여 줍니다. 이 예에서는 `ToString()` 메서드를 사용하여 계층 관계를 보여 줍니다.
  
```sql
DECLARE @SubjectEmployee hierarchyid , @OldParent hierarchyid, @NewParent hierarchyid  
SELECT @SubjectEmployee = OrgNode FROM HumanResources.EmployeeDemo  
  WHERE LoginID = 'adventure-works\gail0' ;  
SELECT @OldParent = OrgNode FROM HumanResources.EmployeeDemo  
  WHERE LoginID = 'adventure-works\roberto0' ; -- who is /1/1/  
SELECT @NewParent = OrgNode FROM HumanResources.EmployeeDemo  
  WHERE LoginID = 'adventure-works\wanida0' ; -- who is /2/3/  
  
SELECT OrgNode.ToString() AS Current_OrgNode_AS_Text,   
(@SubjectEmployee. GetReparentedValue(@OldParent, @NewParent) ).ToString() AS Proposed_OrgNode_AS_Text,  
OrgNode AS Current_OrgNode,  
@SubjectEmployee. GetReparentedValue(@OldParent, @NewParent) AS Proposed_OrgNode,  
*  
FROM HumanResources.EmployeeDemo  
WHERE OrgNode = @SubjectEmployee ;  
GO  
```  
  
### <a name="b-updating-a-node-to-a-new-location"></a>2. 새 위치로 노드 업데이트  
다음 예에서는 UPDATE 문의 `GetReparentedValue()`를 사용하여 계층에서 노드를 이전 위치에서 새 위치로 이동합니다.
  
```sql
DECLARE @SubjectEmployee hierarchyid , @OldParent hierarchyid, @NewParent hierarchyid  
SELECT @SubjectEmployee = OrgNode FROM HumanResources.EmployeeDemo  
  WHERE LoginID = 'adventure-works\gail0' ; -- Node /1/1/2/  
SELECT @OldParent = OrgNode FROM HumanResources.EmployeeDemo  
  WHERE LoginID = 'adventure-works\roberto0' ; -- Node /1/1/  
SELECT @NewParent = OrgNode FROM HumanResources.EmployeeDemo  
  WHERE LoginID = 'adventure-works\wanida0' ; -- Node /2/3/  
  
UPDATE HumanResources.EmployeeDemo  
SET OrgNode = @SubjectEmployee. GetReparentedValue(@OldParent, @NewParent)   
WHERE OrgNode = @SubjectEmployee ;  
  
SELECT OrgNode.ToString() AS Current_OrgNode_AS_Text,   
*  
FROM HumanResources.EmployeeDemo  
WHERE LoginID = 'adventure-works\gail0' ; -- Now node /2/3/2/  
```  
  
### <a name="c-clr-example"></a>C. CLR 예  
다음 코드 조각은 GetReparentedValue() 메서드를 호출합니다.
  
```sql
this. GetReparentedValue(oldParent, newParent)  
```  
  
## <a name="see-also"></a>관련 항목:
[hierarchyid 데이터 형식 메서드 참조](https://msdn.microsoft.com/library/01a050f5-7580-4d5f-807c-7f11423cbb06)  
[계층적 데이터&#40;SQL Server&#41;](../../relational-databases/hierarchical-data-sql-server.md)  
[hierarchyid&#40;Transact-SQL&#41;](../../t-sql/data-types/hierarchyid-data-type-method-reference.md)
  
  
