---
title: SQLGetInfo | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: native-client-odbc-api
ms.reviewer: 
ms.suite: sql
ms.technology: docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apitype: DLLExport
helpviewer_keywords: SQLGetInfo function
ms.assetid: f6215bac-ed3d-4c36-86d5-d56ffbc106aa
caps.latest.revision: "43"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 4a75755a22259e45df1bdcb5f59bbc1e793752b8
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="sqlgetinfo"></a>SQLGetInfo
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  테이블에서 반환 된 값을 보여 줍니다. **SQLGetInfo**합니다. 값은 연결된 서버의 버전 번호에 따라 다를 수 있습니다.  
  
 **SQLGetInfo** 에 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client에서와 다른 **SQLGetInfo** 에 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC 드라이버 (SQLSRV32 합니다. DLL) 때 **SQLGetInfo** SQL_KEYWORDS 및 버퍼 길이 0으로 호출 합니다.  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 드라이버는 SQL_SUCCESS를 반환하지만 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC 드라이버는 SQL_SUCCESS_WITH_INFO를 반환합니다.  하지만 출력 키워드 문자열 보다 작으면 0이 아닌 버퍼 길이 사용 하 여 호출 하는 경우 **SQLGetInfo** 에 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client SQL_SUCCESS_WITH_INFO 및 SQLState 01004 반환 합니다.  
  
|fInfoType|rgbInfoValue|  
|---------------|------------------|  
|SQL_ACCESSIBLE_PROCEDURES|"Y"|  
|SQL_ACCESSIBLE_TABLES|"Y"|  
|SQL_ACTIVE_CONNECTIONS|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서 연결 수가 제한됩니다. 이 0을 반환 하는 드라이버 **SQLGetInfo** 요청 합니다.|  
|SQL_ACTIVE_ENVIRONMENTS|환경 수는 드라이버에서 제한되지 않습니다. 이 0을 반환 하는 드라이버 **SQLGetInfo** 요청 합니다.|  
|SQL_ACTIVE_STATEMENTS|이 대 한 1을 반환 하는 드라이버 **SQLGetInfo** 요청 합니다. 응용 프로그램에 사용할 수 있는 문 핸들 수는 드라이버에서 제한되지 않지만 문 핸들이 기본 실행될 때는 다른 핸들의 실행이 차단됩니다.|  
|SQL_ALTER_DOMAIN|FALSE|  
|SQL_ALTER_TABLE|SQL_AT_ADD_COLUMN SQL_AT_ADD_COLUMN_DEFAULT SQL_AT_ADD_COLUMN_SINGLE SQL_AT_ADD_CONSTRAINT SQL_AT_ADD_TABLE_CONSTRAINTSQL_AT_CONSTRAINT_NAME_DEFINITION SQL_AT_DROP_COLUMN_RESTRICT|  
|SQL_SQL_CONFORMANCE|SQL_SC_SQL92_ENTRY|  
|SQL_DATETIME_LITERALS|FALSE|  
|SQL_ASYNC_MODE|SQL_AM_STATEMENT|  
|SQL_BATCH_ROW_COUNT|SQL_BRC_EXPLICIT|  
|SQL_BATCH_SUPPORT|SQL_BS_ROW_COUNT_EXPLICIT SQL_BS_ROW_COUNT_PROC SQL_BS_SELECT_EXPLICIT SQL_BS_SELECT_PROC|  
|SQL_BOOKMARK_PERSISTENCE|SQL_BP_DELETE SQL_BP_SCROLL SQL_BP_UPDATE|  
|SQL_CATALOG_LOCATION|SQL_CL_START|  
|SQL_CATALOG_NAME|"Y"|  
|SQL_CATALOG_NAME_SEPARATOR|"."|  
|SQL_CATALOG_TERM|"database"|  
|SQL_CATALOG_USAGE|SQL_CU_DML_STATEMENTS SQL_CU_PROCEDURE_INVOCATION SQL_CU_TABLE_DEFINITION|  
|SQL_COLLATION_SEQ|연결 및 서버에 현재 할당된 데이터 정렬 순서입니다.|  
|SQL_COLUMN_ALIAS|"Y"|  
|SQL_CONCAT_NULL_BEHAVIOR|SQL_CB_NULL|  
|SQL_CONVERT_BIGINT|ODBC SQL_BIGINT 데이터 형식의 변환이 지원되지 않습니다. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC 드라이버가 지 원하는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **decimal(19,0)** 데이터 형식을 ODBC 형식 sql_decimal로 지원 합니다. 아래의 SQL_CONVERT_DECIMAL을 참조하십시오.|  
|SQL_CONVERT_BINARY|SQL_CVT_CHAR SQL_CVT_NUMERIC SQL_CVT_DECIMAL SQL_CVT_INTEGER SQL_CVT_SMALLINT SQL_CVT_VARCHAR SQL_CVT_BINARY SQL_CVT_VARBINARY SQL_CVT_TINYINT SQL_CVT_LONGVARBINARY SQL_CVT_WCHAR SQL_CVT_WVARCHAR|  
|SQL_CONVERT_BIT|SQL_CVT_CHAR SQL_CVT_NUMERIC SQL_CVT_DECIMAL SQL_CVT_INTEGER SQL_CVT_SMALLINT SQL_CVT_FLOAT SQL_CVT_REAL SQL_CVT_VARCHAR SQL_CVT_BINARY SQL_CVT_VARBINARY SQL_CVT_BIT SQL_CVT_TINYINT SQL_CVT_WCHAR SQL_CVT_WVARCHAR|  
|SQL_CONVERT_CHAR|SQL_CVT_CHAR SQL_CVT_NUMERIC SQL_CVT_DECIMAL SQL_CVT_INTEGER SQL_CVT_SMALLINT SQL_CVT_FLOAT SQL_CVT_REAL SQL_CVT_VARCHAR SQL_CVT_LONGVARCHAR SQL_CVT_BINARY SQL_CVT_VARBINARY SQL_CVT_BIT SQL_CVT_TINYINT SQL_CVT_TIMESTAMP SQL_CVT_LONGVARBINARY SQL_CVT_WCHAR SQL_CVT_WLONGVARCHAR SQL_CVT_WVARCHAR|  
|SQL_CONVERT_DATE|ODBC SQL_TYPE_DATE 데이터 형식의 변환이 지원되지 않습니다. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC 드라이버가 지 원하는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **datetime** 데이터 형식을 ODBC 형식 SQL_TYPE_TIMESTAMP 합니다. 아래의 SQL_CONVERT_TIMESTAMP를 참조하십시오.|  
|SQL_CONVERT_DECIMAL|SQL_CVT_CHAR SQL_CVT_NUMERIC SQL_CVT_DECIMAL SQL_CVT_INTEGER SQL_CVT_SMALLINT SQL_CVT_FLOAT SQL_CVT_REAL SQL_CVT_VARCHAR SQL_CVT_BINARY SQL_CVT_VARBINARY SQL_CVT_BIT SQL_CVT_TINYINT SQL_CVT_WCHAR SQL_CVT_WVARCHAR|  
|SQL_CONVERT_DOUBLE|ODBC SQL_DOUBLE 데이터 형식의 변환이 지원되지 않습니다. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC 드라이버는 ODBC SQL_DOUBLE 데이터 형식을 SQL_FLOAT로 지원 합니다. 아래의 SQL_CONVERT_FLOAT를 참조하십시오.|  
|SQL_CONVERT_FLOAT|SQL_CVT_CHAR SQL_CVT_NUMERIC SQL_CVT_DECIMAL SQL_CVT_INTEGER SQL_CVT_SMALLINT SQL_CVT_FLOAT SQL_CVT_REAL SQL_CVT_VARCHAR SQL_CVT_BIT SQL_CVT_TINYINT SQL_CVT_WCHAR SQL_CVT_WVARCHAR|  
|SQL_CONVERT_FUNCTIONS|SQL_FN_CVT_CONVERT SQL_FN_CVT_CAST|  
|SQL_CONVERT_INTEGER|SQL_CVT_CHAR SQL_CVT_NUMERIC SQL_CVT_DECIMAL SQL_CVT_INTEGER SQL_CVT_SMALLINT SQL_CVT_FLOAT SQL_CVT_REAL SQL_CVT_VARCHAR SQL_CVT_BINARY SQL_CVT_VARBINARY SQL_CVT_BIT SQL_CVT_TINYINT SQL_CVT_WCHAR SQL_CVT_WVARCHAR|  
|SQL_CONVERT_INTERVAL_YEAR_MONTH|interval 데이터 형식의 변환이 지원되지 않습니다.|  
|SQL_CONVERT_INTERVAL_DAY_TIME|interval 데이터 형식의 변환이 지원되지 않습니다.|  
|SQL_CONVERT_LONGVARBINARY|SQL_CVT_BINARY SQL_CVT_LONGVARBINARY SQL_CVT_VARBINARY|  
|SQL_CONVERT_LONGVARCHAR|SQL_CVT_CHAR SQL_CVT_VARCHAR SQL_CVT_LONGVARCHAR SQL_CVT_WCHAR SQL_CVT_WLONGVARCHAR SQL_CVT_WVARCHAR|  
|SQL_CONVERT_NUMERIC|SQL_CVT_CHAR SQL_CVT_NUMERIC SQL_CVT_DECIMAL SQL_CVT_INTEGER SQL_CVT_SMALLINT SQL_CVT_FLOAT SQL_CVT_REAL SQL_CVT_VARCHAR SQL_CVT_BINARY SQL_CVT_VARBINARY SQL_CVT_BIT SQL_CVT_TINYINT SQL_CVT_WCHAR SQL_CVT_WVARCHAR|  
|SQL_CONVERT_REAL|SQL_CVT_CHAR SQL_CVT_NUMERIC SQL_CVT_DECIMAL SQL_CVT_INTEGER SQL_CVT_SMALLINT SQL_CVT_FLOAT SQL_CVT_REAL SQL_CVT_VARCHAR SQL_CVT_BIT SQL_CVT_TINYINT SQL_CVT_WCHAR SQL_CVT_WVARCHAR|  
|SQL_CONVERT_SMALLINT|SQL_CVT_CHAR SQL_CVT_NUMERIC SQL_CVT_DECIMAL SQL_CVT_INTEGER SQL_CVT_SMALLINT SQL_CVT_FLOAT SQL_CVT_REAL SQL_CVT_VARCHAR SQL_CVT_BINARY SQL_CVT_VARBINARY SQL_CVT_BIT SQL_CVT_TINYINT SQL_CVT_WCHAR SQL_CVT_WVARCHAR|  
|SQL_CONVERT_TIME|ODBC SQL_TYPE_TIME 데이터 형식의 변환이 지원되지 않습니다. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC 드라이버가 지 원하는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **datetime** 데이터 형식을 ODBC 형식 SQL_TYPE_TIMESTAMP 합니다. 아래의 SQL_CONVERT_TIMESTAMP를 참조하십시오.|  
|SQL_CONVERT_TIMESTAMP|SQL_CVT_CHAR SQL_CVT_VARCHAR SQL_CVT_BINARY SQL_CVT_VARBINARY SQL_CVT_TIMESTAMP SQL_CVT_WCHAR SQL_CVT_WVARCHAR|  
|SQL_CONVERT_TINYINT|SQL_CVT_CHAR SQL_CVT_NUMERIC SQL_CVT_DECIMAL SQL_CVT_INTEGER SQL_CVT_SMALLINT SQL_CVT_FLOAT SQL_CVT_REAL SQL_CVT_VARCHAR SQL_CVT_BINARY SQL_CVT_VARBINARY SQL_CVT_BIT SQL_CVT_TINYINT SQL_CVT_WCHAR SQL_CVT_WVARCHAR|  
|SQL_CONVERT_VARBINARY|SQL_CVT_CHAR SQL_CVT_NUMERIC SQL_CVT_DECIMAL SQL_CVT_INTEGER SQL_CVT_SMALLINT SQL_CVT_VARCHAR SQL_CVT_BINARY SQL_CVT_VARBINARY SQL_CVT_TINYINT SQL_CVT_LONGVARBINARY SQL_CVT_WCHAR SQL_CVT_WVARCHAR|  
|SQL_CONVERT_VARCHAR|SQL_CVT_CHAR SQL_CVT_NUMERIC SQL_CVT_DECIMAL SQL_CVT_INTEGER SQL_CVT_SMALLINT SQL_CVT_FLOAT SQL_CVT_REAL SQL_CVT_VARCHAR SQL_CVT_LONGVARCHAR SQL_CVT_BINARY SQL_CVT_VARBINARY SQL_CVT_BIT SQL_CVT_TINYINT SQL_CVT_TIMESTAMP SQL_CVT_LONGVARBINARY SQL_CVT_WCHAR SQL_CVT_WLONGVARCHAR SQL_CVT_WVARCHAR|  
|SQL_CONVERT_WCHAR|SQL_CVT_CHAR SQL_CVT_NUMERIC SQL_CVT_DECIMAL SQL_CVT_INTEGER SQL_CVT_SMALLINT SQL_CVT_FLOAT SQL_CVT_REAL SQL_CVT_VARCHAR SQL_CVT_LONGVARCHAR SQL_CVT_BINARY SQL_CVT_VARBINARY SQL_CVT_BIT SQL_CVT_TINYINT SQL_CVT_TIMESTAMP SQL_CVT_LONGVARBINARY SQL_CVT_WCHAR SQL_CVT_WLONGVARCHAR SQL_CVT_WVARCHAR|  
|SQL_CONVERT_WLONGVARCHAR|SQL_CVT_CHAR SQL_CVT_VARCHAR SQL_CVT_LONGVARCHAR SQL_CVT_WCHAR SQL_CVT_WLONGVARCHAR SQL_CVT_WVARCHAR|  
|SQL_CONVERT_WVARCHAR|SQL_CVT_CHAR SQL_CVT_NUMERIC SQL_CVT_DECIMAL SQL_CVT_INTEGER SQL_CVT_SMALLINT SQL_CVT_FLOAT SQL_CVT_REAL SQL_CVT_VARCHAR SQL_CVT_LONGVARCHAR SQL_CVT_BINARY SQL_CVT_VARBINARY SQL_CVT_BIT SQL_CVT_TINYINT SQL_CVT_TIMESTAMP SQL_CVT_LONGVARBINARY SQL_CVT_WCHAR SQL_CVT_WLONGVARCHAR SQL_CVT_WVARCHAR|  
|SQL_CORRELATION_NAME|SQL_CN_ANY|  
|SQL_CREATE_ASSERTION|FALSE|  
|SQL_CREATE_CHARACTER_SET|FALSE|  
|SQL_CREATE_COLLATION|FALSE|  
|SQL_CREATE_DOMAIN|FALSE|  
|SQL_CREATE_SCHEMA|SQL_CS_AUTHORIZATION SQL_CS_CREATE_SCHEMA|  
|SQL_CREATE_TABLE|SQL_CT_CREATE_TABLE|  
|SQL_CREATE_TRANSLATION|FALSE|  
|SQL_CREATE_VIEW|SQL_CV_CHECK_OPTION SQL_CV_CREATE_VIEW|  
|SQL_CURSOR_COMMIT_BEHAVIOR|SQL_CB_CLOSE|  
|SQL_CURSOR_ROLLBACK_BEHAVIOR|SQL_CB_CLOSE|  
|SQL_CURSOR_SENSITIVITY|SQL_SENSITIVE|  
|SQL_DATA_SOURCE_NAME|현재 데이터 원본 이름입니다. 가 가리키는 값을 설정 *StringLengthPtr* 연결 데이터 원본 이름을 지정 하지 않은 경우 0입니다.|  
|SQL_DATA_SOURCE_READ_ONLY|연결 특성 SQL_ATTR_ACCESS_MODE의 설정에 따라 결정됩니다.|  
|SQL_DATABASE_NAME|연결의 현재 데이터베이스입니다.|  
|SQL_DBMS_NAME|"Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]"|  
|SQL_DBMS_VER|연결된 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 인스턴스의 버전 번호입니다.|  
|SQL_DEFAULT_TXN_ISOLATION|SQL_TXN_READ_COMMITTED|  
|SQL_DESCRIBE_PARAMETER|"Y"|  
|SQL_DRIVER_NAME|"sqlncli11.dll"|  
|SQL_DRIVER_ODBC_VER|드라이버가 지원하는 ODBC 버전입니다.|  
|SQL_DRIVER_VER|드라이버의 버전 번호입니다.|  
|SQL_DROP_ASSERTION|FALSE|  
|SQL_DROP_CHARACTER_SET|FALSE|  
|SQL_DROP_COLLATION|FALSE|  
|SQL_DROP_DOMAIN|FALSE|  
|SQL_DROP_SCHEMA|지원되지 않는 DROP SCHEMA입니다.|  
|SQL_DROP_TABLE|SQL_DT_DROP_TABLE|  
|SQL_DROP_TRANSLATION|FALSE|  
|SQL_DROP_VIEW|SQL_DV_DROP_VIEW|  
|SQL_DYNAMIC_CURSOR_ATTRIBUTES1|SQL_CA1_ABSOLUTE SQL_CA1_BULK_ADD SQL_CA1_LOCK_NO_CHANGE SQL_CA1_NEXT SQL_CA1_POS_DELETE SQL_CA1_POS_POSITION SQL_CA1_POS_REFRESH SQL_CA1_POS_UPDATE SQL_CA1_POSITIONED_UPDATE SQL_CA1_POSITIONED_DELETE SQL_CA1_RELATIVE SQL_CA1_SELECT_FOR_UPDATE|  
|SQL_DYNAMIC_CURSOR_ATTRIBUTES2|SQL_CA2_LOCK_CONCURRENCY SQL_CA2_MAX_ROWS_CATALOG SQL_CA2_MAX_ROWS_DELETE SQL_CA2_MAX_ROWS_INSERT SQL_CA2_MAX_ROWS_SELECT SQL_CA2_MAX_ROWS_UPDATE SQL_CA2_OPT_ROWVER_CONCURRENCY SQL_CA2_OPT_VALUES_CONCURRENCY SQL_CA2_READ_ONLY_CONCURRENCY SQL_CA2_SENSITIVITY_ADDITIONS SQL_CA2_SENSITIVITY_UPDATES SQL_CA2_SIMULATE_UNIQUE|  
|SQL_EXPRESSIONS_IN_ORDERBY|"Y"|  
|SQL_FETCH_DIRECTION|SQL_FD_FETCH_ABSOLUTE SQL_FD_FETCH_BOOKMARK SQL_FD_FETCH_FIRST SQL_FD_FETCH_LAST SQL_FD_FETCH_NEXT SQL_FD_FETCH_PRIOR SQL_FD_FETCH_RELATIVE|  
|SQL_FILE_USAGE|SQL_FILE_NOT_SUPPORTED|  
|SQL_FORWARD_ONLY_CURSOR_ATTRIBUTES1|SQL_CA1_NEXT SQL_CA1_POSITIONED_DELETE SQL_CA1_POSITIONED_UPDATE SQL_CA1_SELECT_FOR_UPDATE|  
|SQL_FORWARD_ONLY_CURSOR_ATTRIBUTES2|SQL_CA2_LOCK_CONCURRENCY SQL_CA2_MAX_ROWS_CATALOG SQL_CA2_MAX_ROWS_DELETE SQL_CA2_MAX_ROWS_INSERT SQL_CA2_MAX_ROWS_SELECT SQL_CA2_MAX_ROWS_UPDATE SQL_CA2_OPT_ROWVER_CONCURRENCY SQL_CA2_OPT_VALUES_CONCURRENCY SQL_CA2_READ_ONLY_CONCURRENCY|  
|SQL_GETDATA_EXTENSIONS|SQL_GD_BLOCK|  
|SQL_GROUP_BY|SQL_GB_GROUP_BY_CONTAINS_SELECT|  
|SQL_IDENTIFIER_CASE|대/소문자 구분 안 함 정렬 순서를 실행하는 서버에 연결된 경우 SQL_IC_MIXED입니다.<br /><br /> 대/소문자 구분 정렬 순서를 실행하는 서버에 연결된 경우 SQL_IC_SENSITIVE입니다.|  
|SQL_IDENTIFIER_QUOTE_CHAR|"(큰따옴표)|  
|SQL_INDEX_KEYWORDS|SQL_IK_ASC SQL_IK_DESC|  
|SQL_INFO_SCHEMA_VIEWS|드라이버에서 지원하지 않는 요청입니다.|  
|SQL_INFO_SS_NETLIB_NAME|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC 드라이버 관련 특성입니다. 연결에서 사용하는 네트워크 라이브러리의 이름입니다.<br /><br /> 기본적으로 DBNETLIB가 반환 됩니다.  이 경우 DBNETLIB는 네트워크 라이브러리 나타내며 dbnetlib.dll 관련이 없는.|  
|SQL_INTEGRITY|"Y"|  
|SQL_KEYSET_CURSOR_ATTRIBUTES1|SQL_CA1_ABSOLUTE SQL_CA1_BOOKMARK SQL_CA1_BULK_ADD SQL_CA1_BULK_DELETE_BY_BOOKMARK SQL_CA1_BULK_FETCH_BY_BOOKMARK SQL_CA1_BULK_UPDATE_BY_BOOKMARK SQL_CA1_LOCK_NO_CHANGE SQL_CA1_NEXT SQL_CA1_POS_DELETE SQL_CA1_POS_POSITION SQL_CA1_POS_REFRESH SQL_CA1_POS_UPDATE SQL_CA1_POSITIONED_DELETE SQL_CA1_POSITIONED_UPDATE SQL_CA1_RELATIVE SQL_CA1_SELECT_FOR_UPDATE|  
|SQL_KEYSET_CURSOR_ATTRIBUTES2|SQL_CA2_CRC_EXACT SQL_CA2_LOCK_CONCURRENCY SQL_CA2_MAX_ROWS_CATALOG SQL_CA2_MAX_ROWS_DELETE SQL_CA2_MAX_ROWS_INSERT SQL_CA2_MAX_ROWS_SELECT SQL_CA2_MAX_ROWS_UPDATE SQL_CA2_OPT_ROWVER_CONCURRENCY SQL_CA2_OPT_VALUES_CONCURRENCY SQL_CA2_READ_ONLY_CONCURRENCY SQL_CA2_SENSITIVITY_ADDITIONS SQL_CA2_SENSITIVITY_UPDATES SQL_CA2_SIMULATE_UNIQUE|  
|SQL_KEYWORDS|BREAK BROWSE BULK CHECKPOINT CLUSTERED COMMITTED COMPUTE CONFIRM CONTROLROW DATABASE DBCC DISK DISTRIBUTED DUMMY DUMP ERRLVL ERROREXIT EXIT FILE FILLFACTOR FLOPPY HOLDLOCK IDENTITY_INSERT IDENTITYCOL IF KILL LINENO LOAD MIRROREXIT NONCLUSTERED OFF OFFSETS ONCE OVER PERCENT PERM PERMANENT PLAN PRINT PROC PROCESSEXIT RAISERROR READ READTEXT RECONFIGURE REPEATABLE RETURN ROWCOUNT RULE SAVE SERIALIZABLE SETUSER SHUTDOWN STATISTICS TAPE TEMP TEXTSIZE TRAN TRIGGER TRUNCATE TSEQUEL UNCOMMITTED UPDATETEXT USE WAITFOR WHILE WRITETEXT|  
|SQL_LIKE_ESCAPE_CLAUSE|"Y"|  
|SQL_LOCK_TYPES|SQL_LCK_NO_CHANGE|  
|SQL_MAX_ASYNC_CONCURRENT_STATEMENTS|1.|  
|SQL_MAX_BINARY_LITERAL_LEN|131072|  
|SQL_MAX_CATALOG_NAME_LEN|128|  
|SQL_MAX_CHAR_LITERAL_LEN|131072|  
|SQL_MAX_COLUMN_NAME_LEN|128|  
|SQL_MAX_COLUMNS_IN_GROUP_BY|16|  
|SQL_MAX_COLUMNS_IN_INDEX|16|  
|SQL_MAX_COLUMNS_IN_ORDER_BY|16|  
|SQL_MAX_COLUMNS_IN_SELECT|4000|  
|SQL_MAX_COLUMNS_IN_TABLE|250|  
|SQL_MAX_CONCURRENT_ACTIVITIES|1.|  
|SQL_MAX_CURSOR_NAME_LEN|128|  
|SQL_MAX_DRIVER_CONNECTIONS|0|  
|SQL_MAX_IDENTIFIER_LEN|128|  
|SQL_MAX_INDEX_SIZE|127|  
|SQL_MAX_PROCEDURE_NAME_LEN|134|  
|SQL_MAX_ROW_SIZE|8062|  
|SQL_MAX_ROW_SIZE_INCLUDES_LONG|"N"|  
|SQL_MAX_SCHEMA_NAME_LEN|128|  
|SQL_MAX_STATEMENT_LEN|131072|  
|SQL_MAX_TABLE_NAME_LEN|128|  
|SQL_MAX_TABLES_IN_SELECT|16|  
|SQL_MAX_USER_NAME_LEN|128|  
|SQL_MAX_OWNER_NAME_LEN|128|  
|SQL_MAX_QUALIFIER_NAME_LEN|128|  
|SQL_MULT_RESULT_SETS|"Y"|  
|SQL_MULTIPLE_ACTIVE_TXN|"Y"|  
|SQL_NEED_LONG_DATA_LEN|"Y"|  
|SQL_NON_NULLABLE_COLUMNS|SQL_NNC_NON_NULL|  
|SQL_NULL_COLLATION|SQL_NC_LOW|  
|SQL_NUMERIC_FUNCTIONS|SQL_FN_NUM_ABS SQL_FN_NUM_ACOS SQL_FN_NUM_ASIN SQL_FN_NUM_ATAN SQL_FN_NUM_ATAN2 SQL_FN_NUM_CEILING SQL_FN_NUM_COS SQL_FN_NUM_COT SQL_FN_NUM_DEGREES SQL_FN_NUM_EXP SQL_FN_NUM_FLOOR SQL_FN_NUM_LOG SQL_FN_NUM_LOG10 SQL_FN_NUM_MOD SQL_FN_NUM_PI SQL_FN_NUM_POWER SQL_FN_NUM_RADIANS SQL_FN_NUM_RAND SQL_FN_NUM_ROUND SQL_FN_NUM_SIGN SQL_FN_NUM_SIN SQL_FN_NUM_SQRT SQL_FN_NUM_TAN|  
|SQL_ODBC_API_CONFORMANCE|SQL_OAC_LEVEL2|  
|SQL_ODBC_SAG_CLI_CONFORMANCE|SQL_OSCC_NOT_COMPLIANT|  
|SQL_ODBC_SQL_CONFORMANCE|SQL_OSC_CORE|  
|SQL_ODBC_SQL_OPT_IEF|"Y"|  
|SQL_ODBC_VER|ODBC 드라이버 관리자의 현재 버전 번호입니다.|  
|SQL_OJ_CAPABILITIES|SQL_OJ_ALL_COMPARISON_OPS SQL_OJ_FULL SQL_OJ_INNER SQL_OJ_LEFT SQL_OJ_NESTED SQL_OJ_NOT_ORDERED SQL_OJ_RIGHT|  
|SQL_OUTER_JOINS|"Y"|  
|SQL_ORDER_BY_COLUMNS_IN_SELECT|"N"|  
|SQL_OWNER_USAGE|SQL_OU_DML_STATEMENTS SQL_OU_INDEX_DEFINITION SQL_OU_PRIVILEGE_DEFINITION SQL_OU_PROCEDURE_INVOCATION SQL_OU_TABLE_DEFINITION|  
|SQL_PARAM_ARRAY_ROW_COUNTS|SQL_PARC_BATCH|  
|SQL_PARAM_ARRAY_SELECTS|SQL_PAS_BATCH|  
|SQL_POS_OPERATIONS|SQL_POS_ADD SQL_POS_DELETE SQL_POS_POSITION SQL_POS_REFRESH SQL_POS_UPDATE|  
|SQL_POSITIONED_STATEMENTS|SQL_PS_POSITIONED_DELETE SQL_PS_POSITIONED_UPDATE SQL_PS_SELECT_FOR_UPDATE|  
|SQL_PROCEDURE_TERM|"stored procedure"|  
|SQL_PROCEDURES|"Y"|  
|SQL_QUALIFIER_USAGE|SQL_CU_DML_STATEMENTS SQL_CU_PROCEDURE_INVOCATION SQL_CU_TABLE_DEFINITION|  
|SQL_QUOTED_IDENTIFIER_CASE|대/소문자 구분 안 함 정렬 순서를 실행하는 서버에 연결된 경우 SQL_IC_MIXED입니다.<br /><br /> 대/소문자 구분 정렬 순서를 실행하는 서버에 연결된 경우 SQL_IC_SENSITIVE입니다.|  
|SQL_ROW_UPDATES|"N"|  
|SQL_SCHEMA_TERM|"owner"|  
|SQL_SCHEMA_USAGE|SQL_OU_DML_STATEMENTS SQL_OU_INDEX_DEFINITION SQL_OU_PRIVILEGE_DEFINITION SQL_OU_PROCEDURE_INVOCATION SQL_OU_TABLE_DEFINITION|  
|SQL_SCROLL_OPTIONS|SQL_SO_DYNAMIC SQL_SO_FORWARD_ONLY SQL_SO_KEYSET_DRIVEN SQL_SO_STATIC|  
|SQL_SCROLL_CONCURRENCY|SQL_SCCO_LOCK SQL_SCCO_OPT_ROWVER SQL_SCCO_OPT_VALUES SQL_SCCO_READ_ONLY|  
|SQL_SEARCH_PATTERN_ESCAPE|"\\"|  
|SQL_SERVER_NAME|연결의 서버 이름입니다.|  
|SQL_SPECIAL_CHARACTERS|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서 설치한 문자 집합에 따라 결정됩니다.|  
|SQL_SQL92_DATETIME_FUNCTIONS|FALSE|  
|SQL_SQL92_FOREIGN_KEY_DELETE_RULE|FALSE|  
|SQL_SQL92_FOREIGN_KEY_UPDATE_RULE|FALSE|  
|SQL_SQL92_GRANT|SQL_SG_WITH_GRANT_OPTION|  
|SQL_SQL92_NUMERIC_VALUE_FUNCTIONS|FALSE|  
|SQL_SQL92_PREDICATES|SQL_SP_EXISTS SQL_SP_ISNOTNULL SQL_SP_ISNULL SQL_SP_LIKE SQL_SP_IN SQL_SP_BETWEEN SQL_SP_UNIQUE|  
|SQL_SQL92_RELATIONAL_JOIN_OPERATORS|SQL_SRJO_CROSS_JOIN SQL_SRJO_FULL_OUTER_JOIN SQL_SRJO_INNER_JOIN SQL_SRJO_LEFT_OUTER_JOIN SQL_SRJO_RIGHT_OUTER_JOIN SQL_SRJO_UNION_JOIN|  
|SQL_SQL92_REVOKE|SQL_SR_GRANT_OPTION_FOR|  
|SQL_SQL92_ROW_VALUE_CONSTRUCTOR|SQL_SRVC_DEFAULT SQL_SRVC_NULL SQL_SRVC_ROW_SUBQUERY SQL_SRVC_VALUE_EXPRESSION|  
|SQL_SQL92_STRING_FUNCTIONS|SQL_SSF_LOWER SQL_SSF_UPPER|  
|SQL_SQL92_VALUE_EXPRESSIONS|SQL_SVE_CASE SQL_SVE_CAST SQL_SVE_COALESCE SQL_SVE_NULLIF|  
|SQL_STANDARD_CLI_CONFORMANCE|SQL_SCC_ISO92_CLI|  
|SQL_STATIC_CURSOR_ATTRIBUTES1|SQL_CA1_ABSOLUTE SQL_CA1_BOOKMARK SQL_CA1_BULK_FETCH_BY_BOOKMARK SQL_CA1_LOCK_NO_CHANGE SQL_CA1_NEXT SQL_CA1_POS_POSITION SQL_CA1_POS_REFRESH SQL_CA1_RELATIVE|  
|SQL_STATIC_CURSOR_ATTRIBUTES2|SQL_CA2_CRC_EXACT SQL_CA2_MAX_ROWS_CATALOG SQL_CA2_MAX_ROWS_DELETE SQL_CA2_MAX_ROWS_INSERT SQL_CA2_MAX_ROWS_SELECT SQL_CA2_MAX_ROWS_UPDATE SQL_CA2_READ_ONLY_CONCURRENCY|  
|SQL_STATIC_SENSITIVITY|SQL_SS_ADDITIONS SQL_SS_UPDATES|  
|SQL_STRING_FUNCTIONS|SQL_FN_STR_ASCII SQL_FN_STR_BIT_LENGTH SQL_FN_STR_CHAR SQL_FN_STR_CONCAT SQL_FN_STR_DIFFERENCE SQL_FN_STR_INSERT SQL_FN_STR_LCASE SQL_FN_STR_LEFT SQL_FN_STR_LENGTH SQL_FN_STR_LOCATE_2 SQL_FN_STR_LTRIM SQL_FN_STR_OCTET_LENGTH SQL_FN_STR_REPEAT SQL_FN_STR_RIGHT SQL_FN_STR_RTRIM SQL_FN_STR_SOUNDEX SQL_FN_STR_SPACE SQL_FN_STR_SUBSTRING SQL_FN_STR_UCASE|  
|SQL_SUBQUERIES|SQL_SQ_COMPARISON SQL_SQ_CORRELATED_SUBQUERIES SQL_SQ_EXISTS SQL_SQ_IN SQL_SQ_QUANTIFIED|  
|SQL_SYSTEM_FUNCTIONS|SQL_FN_SYS_DBNAME SQL_FN_SYS_IFNULL SQL_FN_SYS_USERNAME|  
|SQL_TABLE_TERM|"table"|  
|SQL_TIMEDATE_ADD_INTERVALS|SQL_FN_TSI_DAY SQL_FN_TSI_FRAC_SECOND SQL_FN_TSI_HOUR SQL_FN_TSI_MINUTE SQL_FN_TSI_MONTH SQL_FN_TSI_QUARTER SQL_FN_TSI_SECOND SQL_FN_TSI_WEEK SQL_FN_TSI_YEAR|  
|SQL_TIMEDATE_DIFF_INTERVALS|SQL_FN_TSI_DAY SQL_FN_TSI_FRAC_SECOND SQL_FN_TSI_HOUR SQL_FN_TSI_MINUTE SQL_FN_TSI_MONTH SQL_FN_TSI_QUARTER SQL_FN_TSI_SECOND SQL_FN_TSI_WEEK SQL_FN_TSI_YEAR|  
|SQL_TIMEDATE_FUNCTIONS|SQL_FN_TD_CURDATE SQL_FN_TD_CURRENT_DATE SQL_FN_TD_CURRENT_TIME SQL_FN_TD_CURRENT_TIMESTAMP SQL_FN_TD_CURTIME SQL_FN_TD_DAYNAME SQL_FN_TD_DAYOFMONTH SQL_FN_TD_DAYOFWEEK SQL_FN_TD_DAYOFYEAR SQL_FN_TD_EXTRACT SQL_FN_TD_HOUR SQL_FN_TD_MINUTE SQL_FN_TD_MONTH SQL_FN_TD_MONTHNAME SQL_FN_TD_NOW SQL_FN_TD_QUARTER SQL_FN_TD_SECOND SQL_FN_TD_TIMESTAMPADD SQL_FN_TD_TIMESTAMPDIFF SQL_FN_TD_WEEK SQL_FN_TD_YEAR|  
|SQL_TXN_CAPABLE|SQL_TC_ALL|  
|SQL_TXN_ISOLATION_OPTION|SQL_TXN_READ_COMMITTED SQL_TXN_READ_UNCOMMITTED SQL_TXN_REPEATABLE_READ SQL_TXN_SERIALIZABLE SQL_TXN_SS_SNAPSHOT|  
|SQL_UNION|SQL_U_UNION SQL_U_UNION_ALL|  
|SQL_USER_NAME|현재 사용자 이름입니다.|  
  
## <a name="see-also"></a>관련 항목:  
 [SQLGetInfo 함수](http://go.microsoft.com/fwlink/?LinkId=59354)   
 [ODBC API 구현 정보](../../relational-databases/native-client-odbc-api/odbc-api-implementation-details.md)  
  
  