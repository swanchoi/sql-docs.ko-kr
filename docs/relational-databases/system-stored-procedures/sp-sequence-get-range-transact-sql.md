---
title: sp_sequence_get_range (TRANSACT-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 08/08/2015
ms.prod: sql
ms.prod_service: database-engine, sql-data-warehouse
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_sequence_get_range
- sp_sequence_get_range_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sequence number object, sp_sequence_get_range procedure
- sp_sequence_get_range
ms.assetid: 8ca6b0c6-8d9c-4eee-b02f-51ddffab4492
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: =azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 66ec81fdc6ebdbecf83791c6fffa5735a37723bc
ms.sourcegitcommit: c44014af4d3f821e5d7923c69e8b9fb27aeb1afd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58527945"
---
# <a name="spsequencegetrange-transact-sql"></a>sp_sequence_get_range(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-asdb-asdw-xxx-md](../../includes/tsql-appliesto-ss2012-asdb-asdw-xxx-md.md)]

  시퀀스 개체에서 시퀀스 값의 범위를 반환합니다. 시퀀스 개체는 요청한 값의 수를 생성 및 실행하고 범위와 관련된 메타데이터를 응용 프로그램에 제공합니다.  
  
 시퀀스 번호에 대 한 자세한 내용은 참조 하세요 [시퀀스 번호](../../relational-databases/sequence-numbers/sequence-numbers.md)합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_sequence_get_range [ @sequence_name = ] N'<sequence>'   
     , [ @range_size = ] range_size  
     , [ @range_first_value = ] range_first_value OUTPUT   
    [, [ @range_last_value = ] range_last_value OUTPUT ]  
    [, [ @range_cycle_count = ] range_cycle_count OUTPUT ]  
    [, [ @sequence_increment = ] sequence_increment OUTPUT ]  
    [, [ @sequence_min_value = ] sequence_min_value OUTPUT ]  
    [, [ @sequence_max_value = ] sequence_max_value OUTPUT ]  
    [ ; ]  
```  
  
## <a name="arguments"></a>인수  
`[ @sequence_name = ] N'sequence'` 시퀀스 개체의 이름입니다. 스키마는 선택 사항입니다. *sequence_name* 됩니다 **nvarchar(776)** 합니다.  
  
`[ @range_size = ] range_size` 시퀀스에서 인출할 값의 수입니다. **@range_size** 됩니다 **bigint**합니다.  
  
`[ @range_first_value = ] range_first_value` 출력 매개 변수는 요청한 범위를 계산 하는 데 사용 된 시퀀스 개체의 첫 번째 (최소 또는 최대) 값을 반환 합니다. **@range_first_value** 됩니다 **sql_variant** 요청에 사용 된 시퀀스 개체와 동일한 기본 형식을 사용 합니다.  
  
`[ @range_last_value = ] range_last_value` 선택적 출력 매개 변수는 요청한 범위의 마지막 값을 반환 합니다. **@range_last_value** 됩니다 **sql_variant** 요청에 사용 된 시퀀스 개체와 동일한 기본 형식을 사용 합니다.  
  
`[ @range_cycle_count = ] range_cycle_count` 선택적 출력 매개 변수는 요청한 범위를 반환 하기 위해 시퀀스 개체 순환 횟수를 반환 합니다. **@range_cycle_count** 됩니다 **int**합니다.  
  
`[ @sequence_increment = ] sequence_increment` 선택적 출력 매개 변수는 요청한 범위를 계산 하는 데 사용 된 시퀀스 개체의 증가값을 반환 합니다. **@sequence_increment** 됩니다 **sql_variant** 요청에 사용 된 시퀀스 개체와 동일한 기본 형식을 사용 합니다.  
  
`[ @sequence_min_value = ] sequence_min_value` 선택적 출력 매개 변수는 시퀀스 개체의 최소값을 반환합니다. **@sequence_min_value** 됩니다 **sql_variant** 요청에 사용 된 시퀀스 개체와 동일한 기본 형식을 사용 합니다.  
  
`[ @sequence_max_value = ] sequence_max_value` 선택적 출력 매개 변수는 시퀀스 개체의 최대값을 반환합니다. **@sequence_max_value** 됩니다 **sql_variant** 요청에 사용 된 시퀀스 개체와 동일한 기본 형식을 사용 합니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 0(성공) 또는 1(실패)  
  
## <a name="remarks"></a>Remarks  
 sys에서 sp_sequence_get_rangeis 합니다. 스키마 sys.sp_sequence_get_range로 참조할 수 있습니다.  
  
### <a name="cycling-sequences"></a>순환 시퀀스  
 필요할 경우 시퀀스 개체는 적절한 횟수로 순환하여 요청한 범위를 처리합니다. 순환 횟수는 `@range_cycle_count`를 통해 호출자에게 반환됩니다.  
  
> [!NOTE]  
>  순환할 때 시퀀스 개체는 시퀀스 개체의 시작 값이 아니라 오름차순 시퀀스에 대해서는 최소값, 내림차순 시퀀스에 대해서는 최대값에서 다시 시작합니다.  
  
### <a name="non-cycling-sequences"></a>비순환 시퀀스  
 요청한 범위의 값 수가 시퀀스 개체에 남아 있는 사용 가능한 값보다 크면 시퀀스 개체에서 요청한 범위를 빼지 않으며 다음 오류 11732가 반환됩니다.  
  
 `The requested range for sequence object '%.*ls' exceeds the maximum or minimum limit. Retry with a smaller range.`  
  
## <a name="permissions"></a>사용 권한  
 시퀀스 개체 또는 시퀀스 개체의 스키마에 대한 UPDATE 권한이 필요합니다.  
  
## <a name="examples"></a>예  
 다음 예제에서는 Test.RangeSeq 라는 시퀀스 개체를 사용 합니다. Test.RangeSeq 순서를 만들려면 다음 문을 사용 합니다.  
  
```  
CREATE SCHEMA Test ;  
GO  
  
CREATE SEQUENCE Test.RangeSeq  
    AS int   
    START WITH 1  
    INCREMENT BY 1  
    MINVALUE 1  
    MAXVALUE 25  
    CYCLE  
    CACHE 10  
;  
```  
  
### <a name="a-retrieving-a-range-of-sequence-values"></a>1. 시퀀스 값의 범위 검색  
 다음 문은 Test.RangeSeq 시퀀스 개체에서 네 개의 시퀀스 번호를 가져오고 사용자에 게 숫자의 첫 번째를 반환 합니다.  
  
```  
DECLARE @range_first_value sql_variant ,   
        @range_first_value_output sql_variant ;  
  
EXEC sp_sequence_get_range  
@sequence_name = N'Test.RangeSeq'  
, @range_size = 4  
, @range_first_value = @range_first_value_output OUTPUT ;  
  
SELECT @range_first_value_output AS FirstNumber ;  
  
```  
  
### <a name="b-returning-all-output-parameters"></a>2. 모든 출력 매개 변수 반환  
 다음 예제에서는 sp_sequence_get_range 프로시저에서 모든 출력 값을 반환 합니다.  
  
```  
DECLARE    
  @FirstSeqNum sql_variant  
, @LastSeqNum sql_variant  
, @CycleCount int  
, @SeqIncr sql_variant  
, @SeqMinVal sql_variant  
, @SeqMaxVal sql_variant ;  
  
EXEC sys.sp_sequence_get_range  
@sequence_name = N'Test.RangeSeq'  
, @range_size = 5  
, @range_first_value = @FirstSeqNum OUTPUT   
, @range_last_value = @LastSeqNum OUTPUT   
, @range_cycle_count = @CycleCount OUTPUT  
, @sequence_increment = @SeqIncr OUTPUT  
, @sequence_min_value = @SeqMinVal OUTPUT  
, @sequence_max_value = @SeqMaxVal OUTPUT ;  
  
-- The following statement returns the output values  
SELECT  
  @FirstSeqNum AS FirstVal  
, @LastSeqNum AS LastVal  
, @CycleCount AS CycleCount  
, @SeqIncr AS SeqIncrement  
, @SeqMinVal AS MinSeq  
, @SeqMaxVal AS MaxSeq ;  
  
```  
  
 `@range_size` 인수를 75와 같이 큰 수로 변경하면 시퀀스 개체가 순환합니다. `@range_cycle_count` 인수를 검사하여 시퀀스 개체 순환 여부와 순환 횟수를 확인하십시오.  
  
### <a name="c-example-using-adonet"></a>3. ADO.NET 사용 예  
 다음 예제에서는 ADO.NET을 사용 하 여는 Test.RangeSeq에서 범위를 가져옵니다.  
  
```  
SqlCommand cmd = new SqlCommand();  
cmd.Connection = conn;  
cmd.CommandType = CommandType.StoredProcedure;  
cmd.CommandText = "sys.sp_sequence_get_range";  
cmd.Parameters.AddWithValue("@sequence_name", "Test.RangeSeq");  
cmd.Parameters.AddWithValue("@range_size", 10);  
  
// Specify an output parameter to retreive the first value of the generated range.  
SqlParameter firstValueInRange = new SqlParameter("@range_first_value", SqlDbType.Variant);  
firstValueInRange.Direction = ParameterDirection.Output;  
cmd.Parameters.Add(firstValueInRange);  
  
conn.Open();  
cmd.ExecuteNonQuery();  
  
// Output the first value of the generated range.  
Console.WriteLine(firstValueInRange.Value);  
  
```  
  
## <a name="see-also"></a>관련 항목  
 [CREATE SEQUENCE&#40;Transact-SQL&#41;](../../t-sql/statements/create-sequence-transact-sql.md)   
 [ALTER SEQUENCE&#40;Transact-SQL&#41;](../../t-sql/statements/alter-sequence-transact-sql.md)   
 [DROP SEQUENCE &#40;Transact-SQL&#41;](../../t-sql/statements/drop-sequence-transact-sql.md)   
 [NEXT VALUE FOR &#40;Transact-SQL&#41;](../../t-sql/functions/next-value-for-transact-sql.md)   
 [시퀀스 번호](../../relational-databases/sequence-numbers/sequence-numbers.md)  
  
  
