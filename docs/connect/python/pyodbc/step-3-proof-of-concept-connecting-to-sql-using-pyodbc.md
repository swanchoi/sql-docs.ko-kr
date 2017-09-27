---
title: "3 단계: pyodbc를 사용 하 여 SQL에 연결 하는 개념 증명 | Microsoft Docs"
ms.custom: 
ms.date: 08/08/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4bfd6e52-817d-4f0a-a33d-11466e3f0484
caps.latest.revision: 2
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: a6aeda8e785fcaabef253a8256b5f6f7a842a324
ms.openlocfilehash: a93a7d4c341cd035faba52e5626608ef362359cd
ms.contentlocale: ko-kr
ms.lasthandoff: 09/21/2017

---
# <a name="step-3-proof-of-concept-connecting-to-sql-using-pyodbc"></a>3 단계: pyodbc를 사용 하 여 SQL에 연결 하는 개념 증명

이 예제에서는 개념 증명을 고려 되어야 합니다.  샘플 코드의 명확성을 위해 간소화 되 고 Microsoft에서 권장 모범 사례 나타내지는지 않습니다.  

**아래의 샘플 스크립트를 실행** test.py, 라는 파일을 만들고 작업을 진행 하면서 각 코드 조각을 추가 합니다. 

```
> python test.py
```
  
## <a name="step-1--connect"></a>1 단계: 연결  
  
```python

import pyodbc 
server = 'tcp:myserver.database.windows.net' 
database = 'mydb' 
username = 'myusername' 
password = 'mypassword' 
cnxn = pyodbc.connect('DRIVER={ODBC Driver 13 for SQL Server};SERVER='+server+';DATABASE='+database+';UID='+username+';PWD='+ password)
cursor = cnxn.cursor()

```  
  
  
## <a name="step-2--execute-query"></a>2 단계: 쿼리를 실행 합니다.  
  
결과 SQL 데이터베이스에 대해 쿼리에서 집합을 검색 하는 cursor.executefunction은 사용할 수 있습니다. 이 함수에서 기본적으로 모든 쿼리를 허용 하 고 cursor.fetchone() 사용 하 여 반복 될 수 있는 결과 집합 반환
  
  
```python
#Sample select query
cursor.execute("SELECT @@version;") 
row = cursor.fetchone() 
while row: 
    print row[0] 
    row = cursor.fetchone()

```  
  
## <a name="step-3--insert-a-row"></a>행을 삽입 하는 3 단계:  
  
이 예제를 실행 하는 방법을 표시 됩니다는 [삽입](/sql-docs/docs/t-sql/statements/insert-transact-sql) 문을에서 응용 프로그램을 보호 하는 매개 변수를 안전 하 게 전달 [SQL 주입](/sql-docs/docs/relational-databases/tables/primary-and-foreign-key-constraints) 값입니다.    
  
  
```python

#Sample insert query
cursor.execute("INSERT SalesLT.Product (Name, ProductNumber, StandardCost, ListPrice, SellStartDate) OUTPUT INSERTED.ProductID VALUES ('SQL Server Express New 20', 'SQLEXPRESS New 20', 0, 0, CURRENT_TIMESTAMP )") 
row = cursor.fetchone()

while row: 
    print 'Inserted Product key is ' + str(row[0]) 
    row = cursor.fetchone()
```  
  `      
  ## <a name="next-steps"></a>다음 단계  
  
자세한 내용은 참조는 [Python 개발자 센터](https://azure.microsoft.com/en-us/develop/python/)합니다.