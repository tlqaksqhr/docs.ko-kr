---
title: "ADO.NET의 데이터 추적"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6a752a5-d2a9-4335-a382-b58690ccb79f
caps.latest.revision: "9"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a71b28a1653b72d212455e99f8aa0101bb74e7a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="data-tracing-in-adonet"></a>ADO.NET의 데이터 추적
ADO.NET에는 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], Oracle, OLE DB 및 ODBC용 .NET 데이터 공급자를 비롯하여 ADO.NET <xref:System.Data.DataSet> 및 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] 네트워크 프로토콜에서 지원되는 기본 제공 데이터 추적 기능이 추가되었습니다.  
  
 데이터 액세스 API 호출을 추적하면 다음과 같은 문제를 진단할 수 있습니다.  
  
-   클라이언트 프로그램과 데이터베이스 간의 스키마 불일치  
  
-   데이터베이스 비가용성 또는 네트워크 라이브러리 문제  
  
-   하드 코딩되거나 응용 프로그램에서 생성된 잘못된 SQL  
  
-   잘못된 프로그래밍 논리  
  
-   여러 ADO.NET 구성 요소 간의 상호 작용 및 ADO.NET과 사용자 구성 요소 간의 상호 작용으로 인한 문제  
  
 다양한 추적 기술을 지원하기 위해 추적을 확장할 수 있으므로 개발자는 응용 프로그램 스택의 모든 수준에서 문제를 추적할 수 있습니다. 추적이 ADO.NET에만 있는 기능은 아니지만 Microsoft 공급자에서는 일반화된 추적 및 계측 API를 사용합니다.  
  
 설정 및 ADO.NET의 관리 되는 추적을 구성 하는 방법에 대 한 자세한 내용은 참조 [데이터 액세스 추적](http://msdn.microsoft.com/library/hh880086.aspx)합니다.  
  
## <a name="accessing-diagnostic-information-in-the-extended-events-log"></a>확장 이벤트 로그에서 진단 정보에 액세스  
 에 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], 데이터 액세스 추적 ([데이터 액세스 추적](http://msdn.microsoft.com/library/hh880086.aspx)) 쉽게 쉽게 클라이언트 이벤트 간의 상관 관계 연결 실패 등의 진단 정보를 사용 하도록 업데이트 되었습니다 서버의 연결 링 버퍼 및 응용 프로그램 성능 정보에서 확장된 이벤트 로그입니다. 확장된 이벤트 로그 읽기에 대 한 정보를 참조 하십시오. [이벤트 세션 데이터 보기](http://msdn.microsoft.com/library/hh710068\(SQL.110\).aspx)합니다.  
  
 연결 동작의 경우 ADO.NET은 클라이언트 연결 ID를 전송합니다. 연결에 실패 하면 연결 링 버퍼에 액세스할 수 있습니다 ([연결 링 버퍼를 사용 하 여 SQL Server 2008의 연결 문제 해결](http://go.microsoft.com/fwlink/?LinkId=207752)) 했는데는 `ClientConnectionID` 필드 및에 대 한 진단 정보를 얻을 연결 오류입니다. 클라이언트 연결 ID는 오류가 발생한 경우에만 링 버퍼에 로그인됩니다. 사전 로그인 패킷을 전송하기 전에 연결에 실패할 경우 클라이언트 연결 ID가 생성되지 않습니다. 클라이언트 연결 ID는 16바이트 GUID입니다. `client_connection_id` 동작이 확장 이벤트 세션에서 이벤트에 추가된 경우 확장 이벤트 대상 출력에서 클라이언트 연결 ID를 찾을 수도 있습니다. 추가 클라이언트 드라이버 진단이 필요한 경우 데이터 액세스 추적을 활성화하고 연결 명령을 다시 실행하여 데이터 액세스 추적에서 `ClientConnectionID` 필드를 관찰할 수 있습니다.  
  
 `SqlConnection.ClientConnectionID` 속성을 사용하여 클라이언트 연결 ID를 프로그래밍 방식으로 가져올 수 있습니다.  
  
 `ClientConnectionID`는 연결을 성공적으로 설정하는 <xref:System.Data.SqlClient.SqlConnection> 개체에 사용할 수 있습니다. 연결 시도에 실패한 경우에는 `ClientConnectionID`을 통해 `SqlException.ToString`를 확인할 수 있습니다.  
  
 또한 ADO.NET은 스레드별 동작 ID를 전송합니다. TRACK_CAUSAILITY 옵션이 설정된 상태로 세션이 시작된 경우 확장 이벤트 세션에 동작 ID가 캡처됩니다. 활성 연결과 관련한 성능 문제의 경우 클라이언트의 데이터 액세스 추적에서 동작 ID(`ActivityID` 필드)를 가져온 다음 확장 이벤트 출력에서 동작 ID를 찾아볼 수 있습니다. 확장 이벤트의 동작 ID는16바이트 GUID(클라이언트 연결 ID의 GUID와는 다름)에 4바이트 시퀀스 번호를 추가한 것입니다. 시퀀스 번호는 스레드 내의 요청 순서를 나타내며 스레드에서 일괄 처리 및 RPC 문의 상대적인 순서를 나타냅니다. `ActivityID`는 현재 데이터 액세스 추적이 활성화된 상태이고 데이터 액세스 추적 구성 단어의 18번째 비트가 ON 상태인 경우 SQL 일괄 처리 문과 RPC 요청에 대해 선택적으로 전송됩니다.  
  
 다음은 [!INCLUDE[tsql](../../../../includes/tsql-md.md)]을 사용하여 링 버퍼에 저장되는 확장 이벤트 세션을 시작하고 RPC 및 일괄 처리 작업에서 클라이언트로부터 전송된 동작 ID를 기록하는 샘플입니다.  
  
```  
create event session MySession on server   
add event connectivity_ring_buffer_recorded,   
add event sql_statement_starting (action (client_connection_id)),   
add event sql_statement_completed (action (client_connection_id)),   
add event rpc_starting (action (client_connection_id)),   
add event rpc_completed (action (client_connection_id))  
add target ring_buffer with (track_causality=on)  
```  
  
## <a name="see-also"></a>참고 항목  
 [.NET Framework의 네트워크 추적](../../../../docs/framework/network-programming/network-tracing.md)  
 [응용 프로그램 추적 및 조율](../../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
