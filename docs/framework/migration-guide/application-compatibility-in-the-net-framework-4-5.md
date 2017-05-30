---
title: ".NET Framework 4.5의 응용 프로그램 호환성 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility, .NET Framework
- breaking changes [.NET Framework]
ms.assetid: 5c50747c-806c-44a9-ac58-5bbe12a284fa
caps.latest.revision: 76
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 19006cc5f24ffc66b92e53e8174c6bd33c249679
ms.openlocfilehash: 5f63c3217b6def96240447501247d22a1058cacf
ms.contentlocale: ko-kr
ms.lasthandoff: 05/22/2017

---
# <a name="application-compatibility-in-the-net-framework-45"></a>.NET Framework 4.5의 응용 프로그램 호환성
이 항목에서는 고객 피드백을 기초로 버그 수정과 변경 내용을 포함하여 .NET Framework 4와 4.5 사이의 응용 프로그램 호환성 문제를 설명합니다. 이러한 변경 내용은 대부분 응용 프로그램에서 프로그래밍을 수정할 필요가 없습니다. 프로그래밍 수정이 필요한 변경 내용은 표의 영향 열을 참조하십시오.  
  
> [!IMPORTANT]
>  [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]는 [!INCLUDE[winxp](../../../includes/winxp-md.md)]에서 지원되지 않습니다.  
  
 .NET Framework 4.5와 4.5.1 간의 호환성 문제는 [4.5.1의 응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)을 참조하세요.  
  
 이 항목에서는 다음 영역의 중요한 변경 내용에 대해 설명합니다.  
  
-   [핵심](#core)  
  
-   [Data](#sql)  
  
-   [네트워킹](#network)  
  
-   [serialization](#serialize)  
  
-   [인쇄](#Printing)  
  
-   [도구 및 리소스](#tools)  
  
-   [ASP.NET](#asp)  
  
-   [ClickOnce](#ClickOnce)  
  
-   [MEF(Managed Extensibility Framework)](#mef)  
  
-   [웹 응용 프로그램](#web)  
  
-   [WCF(Windows Communication Foundation)](#wcf)  
  
-   [Windows Forms](#winForms)  
  
-   [WPF(Windows Presentation Foundation)](#wpf)  
  
-   [Windows WF(Workflow Foundation)](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md#wwf)  
  
-   [XML, XSLT](#xml)  
  
 이 항목에서는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서 사용하지 않는다고 선언된 형식과 멤버에 대해서는 설명하지 않습니다. 이러한 형식과 멤버의 목록은 [클래스 라이브러리의 사용되지 않는 기능](../../../docs/framework/whats-new/whats-obsolete.md)을 참조하세요. 새 기능에 대한 자세한 내용은 [새로운 기능](../../../docs/framework/whats-new/index.md)을 참조하세요.  
  
<a name="core"></a>   
## <a name="core"></a>핵심  
 다음 응용 프로그램 호환성 문제 외에 [Serialization](#serialize) 섹션의 serialization 관련 문제를 참조하세요.  
  
|기능|변경|영향|  
|-------------|------------|------------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName> 및 <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%2A?displayProperty=fullName> 메서드|<xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName> 메서드는 더 이상 -1을 반환하거나 예외를 throw하지 않습니다. <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%2A?displayProperty=fullName> 메서드는 컬렉션 중 하나가 완료됨으로 표시될 경우 더 이상 예외를 throw하지 않습니다.|이러한 변경을 통해 컬렉션 중 하나가 비어 있거나 완료되었더라도 나머지 컬렉션에는 검색할 수 있는 항목이 아직 있는 경우 컬렉션을 사용할 수 있습니다.|  
|<xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=fullName>|컴파일된 정규식의 어셈블리가 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 로 작성되었지만 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]를 대상으로 하는 경우 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 가 설치된 시스템에서 해당 어셈블리의 정규식 중 하나를 사용하려고 하면 예외가 throw됩니다.|이 문제를 해결하기 위해서는 다음 중 하나를 수행합니다.<br /><br /> [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]를 사용하여 정규식이 포함된 어셈블리를 빌드합니다.<br /><br /> 해석된 정규식을 사용합니다.|  
|<xref:System.Threading.Tasks.Task?displayProperty=fullName> 삭제|`Task.IAsyncResult.AsyncWaitHandle`을 제외하고, <xref:System.Threading.Tasks.Task?displayProperty=fullName> 메서드는 개체가 삭제된 다음 <xref:System.ObjectDisposedException> 예외를 더 이상 throw하지 않습니다.|이 변경은 캐시된 작업의 사용을 지원합니다. 예를 들어, 메서드는 새로운 작업을 할당하는 대신에 이미 완료된 작업을 나타내기 위해 캐시된 작업을 반환할 수 있습니다. 작업의 모든 소비자는 다시 사용할 수 없게 렌더링된 작업을 삭제할 수 있었기 때문에 이전 .NET Framework 버전에서는 이것이 불가능했습니다.|  
|<xref:System.Threading.Tasks.Task?displayProperty=fullName> 작업에서 관찰되지 않은 예외|<xref:System.Threading.Tasks.Task?displayProperty=fullName> 클래스는 비동기 작업을 나타내기 때문에 비동기 처리를 하는 동안 발생하는 심각하지 않은 예외를 모두 catch합니다. [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서는 예외가 관찰되지 않고 코드가 작업에서 대기하지 않으면 예외는 더 이상 종료자 스레드에서 전파되지 않고 가비지 수집 도중 프로세스와 충돌합니다.|이러한 변경으로 인해 관찰되지 않은 비동기 처리를 수행하기 위해 <xref:System.Threading.Tasks.Task> 클래스를 사용하는 응용 프로그램의 안정성이 향상됩니다. 이전 동작은 <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=fullName> 이벤트에 적적한 처리기를 제공하여 복원할 수 있습니다.|  
|제한 시간 인수가 있는 <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=fullName> 메서드|[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서는 이러한 메서드가 일관되지 않게 동작했었습니다. 제한 시간이 만료되고 메서드 호출 전에 하나 이상의 작업이 완료되거나 취소되면 이 메서드는 <xref:System.AggregateException> 예외를 throw합니다. 제한 시간이 만료되고 메서드 호출 전에 완료되거나 취소된 작업은 없지만 메서드 호출 후에 하나 이상의 작업이 완료되거나 취소되면 이 메서드는 `false`를 반환합니다.<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서, 시간 제한 간격이 만료될 때 모든 작업이 아직 실행되고 있는 경우 이러한 메서드 오버로드에서 이제 `false`를 반환하고, 입력 작업이 취소되고(메서드 호출 전후에 취소되었는지 여부와 상관없이) 다른 작업이 실행되고 있지 않은 경우에만 <xref:System.AggregateException> 예외를 throw합니다.|이 변경은 메서드 동작을 일관성 있게 만들어줍니다. 그러나 하나 이상의 작업에 이미 오류가 발생했거나 제한 시간 만료 전에 작업이 취소되었을 때 예외를 throw하는 시간 제한 설정 <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=fullName> 오버로드에 따라 응용 프로그램 코드가 달라질 수 있으나 가능성이 낮습니다. 이 경우에 같은 용도로 <xref:System.Threading.Tasks.Task.IsCanceled%2A?displayProperty=fullName> 속성을 사용할 수 있습니다.|  
|멀티 타기팅 시 형식 전달 지원|새로운 CodeDOM 기능을 통해 컴파일러가 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 버전의 mscorlib.dll 대신 대상 버전의 mscorlib.dll에 대해 컴파일할 수 있습니다.|이러한 변경을 통해 CodeDOM에서 형식이 전달된 형식에 대한 두 가지 정의를 찾을 경우 컴파일러 경고(및 경고가 오류로 처리되는 경우 컴파일 오류)를 방지합니다. 이러한 변경으로 인한 부작용은 서로 다른 버전의 참조 어셈블리가 단일 위치에 혼합되어 있는 경우에만 발생할 수 있습니다.|  
|<xref:System.Collections.Generic.List%601.ForEach%2A?displayProperty=fullName>|열거자는 컬렉션의 요소가 수정된 경우 <xref:System.InvalidOperationException> 예외를 throw합니다.|이 변경은 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]를 대상으로 하는 응용 프로그램에만 적용되며 부정적인 영향이 없어야 합니다. 이를 통해 데이터 무결성을 보호하고 경합 상태가 확인될 가능성이 높아집니다.|  
|<xref:System.Uri?displayProperty=fullName>|IRI(International Resource Identifier) 구문 분석의 두 가지 변경 내용이 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]를 대상으로 하는 응용 프로그램에서 URI에 영향을 미칩니다.<br /><br /> [\<iriParsing>](../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)이 기본적으로 사용하도록 설정되어 있으며 해제할 수 없습니다. 이전에는 기본적으로 비활성화되어 있었습니다.<br /><br /> 유니코드 NFC(정규화 형식 C)는 URI의 비호스트 부분에서는 더 이상 수행되지 않습니다. 이전에는 `<iriParsing>`이 사용하도록 설정되어 있을 때 전체 URI에서 NFC가 수행되었습니다.|NFC(정규화 형식 C)가 아닌 정규화 파일 이름을 포함하는 URI는 형식 C로 정규화되지 않습니다. IRI 구문 분석에서 정규화되지 않은 문자열을 사용하여 파일 이름이 정규화된 파일에 액세스할 경우 응용 프로그램 오류가 발생할 수 있습니다. 이는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]를 대상으로 하는 응용 프로그램에만 영향을 줍니다.|  
|<xref:System.Uri?displayProperty=fullName>|잘못된 `mailto:` URL은 <xref:System.Uri> 클래스 생성자에서 예외를 throw합니다.|이는 다시 컴파일되고 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]를 대상으로 하는 응용 프로그램에만 영향을 미칩니다.|  
|<xref:System.Uri?displayProperty=fullName>|[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]를 대상으로 하는 응용 프로그램에서는 원래 URI 문자열의 패스 세그먼트 끝에 있는 후행 점이 유지됩니다(예: `http://www.proseware.com/LLC./About.aspx`). `http://www.proseware.com/..` 또는 `http://www.proseware.com/./default.htm`과 같이 정확히 하나 또는 두 개의 점으로 구성된 경로 세그먼트는 제거되지만 세 개 이상의 연속된 점이 있는 경로 세그먼트(예: `http://localhost/dir1/.../dir2`)는 유지됩니다.|이러한 변경 내용은 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]를 대상으로 하는 응용 프로그램에만 영향을 줍니다. 제거되는 후행 점을 사용하는 응용 프로그램은 오류가 발생할 수 있습니다.|  
|<xref:System.Uri?displayProperty=fullName>|[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]를 대상으로 하는 응용 프로그램의 경우 `file://` URI의 쿼리는 허용되지만 ? 문자는 경로의 일부로 해석되므로 이스케이프되지 않습니다.|이러한 변경 내용은 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]를 대상으로 하는 응용 프로그램에만 영향을 줍니다. ? 문자의 이스케이프를 사용하는 응용 프로그램은 문자로 인해 오류가 발생할 수 있습니다.|  
|<xref:System.Uri?displayProperty=fullName>|[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]를 대상으로 하는 응용 프로그램에서 U+0080 ~ U+009F의 유니코드 제어 문자가 올바르지 않게 인코딩되었습니다.|일반적으로 유니코드 제어 문자는 URI에서 사용되지 않습니다.|  
|<xref:System.Uri.EscapeDataString%2A?displayProperty=fullName>, <xref:System.Uri.EscapeUriString%2A?displayProperty=fullName> 및 <xref:System.Uri.UnescapeDataString%2A?displayProperty=fullName>|이제 예약된 문자와 예약되지 않은 문자의 목록은 [RFC 3986](http://tools.ietf.org/html/rfc3986)을 지원합니다.|특정 변경 내용:<br /><br /> <xref:System.Uri.EscapeDataString%2A>은 RFC 3986을 기반으로 하는 예약된 문자를 이스케이프합니다.<br /><br /> <xref:System.Uri.EscapeUriString%2A>은 예약된 문자를 이스케이프하지 않습니다.<br /><br /> <xref:System.Uri.UnescapeDataString%2A>은 잘못된 이스케이프 시퀀스가 발생하는 경우 예외를 throw하지 않습니다.<br /><br /> 예약되지 않은 이스케이프된 문자는 이스케이프 해제됩니다.|  
|<xref:System.Uri.IsWellFormedUriString%2A?displayProperty=fullName>|.NET Framework 4.5부터, 문자열은 [RFC 3986](http://tools.ietf.org/html/rfc3986) 및 [RFC 3987](http://tools.ietf.org/html/rfc3987)에 따른 올바른 형식으로 항상 간주됩니다. 이전 버전의 .NET Framework에서 문자열은 URI 구문 분석 및 IDN 구문 분석이 활성화된 경우에만 RFC 3986 및RFC 3987에 따른 올바른 형식으로 간주됩니다.|.NET Framework 4.5 이상의 버전을 대상으로 하는 앱의 경우, 이 메서드는 이전 버전의 .NET Framework를 대상으로 하는 앱에서 올바른 형식으로 간주되는 일부 URI에 대해 `false`를 반환합니다. 예를 들어, 첫 번째 세그먼트(예: "2013.05.29_14:33:41")에 콜론을 포함하는 상대 URI는 더 이상 올바른 형식으로 간주되지 않습니다.<br /><br /> 이 변경은 .NET Framework 4.5 이상의 버전을 대상으로 하는 앱에만 영향을 줍니다.|  
|<xref:System.Threading.Tasks.TaskFactory.FromAsync%2A?displayProperty=fullName>|이제 <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A?displayProperty=fullName>은(는) <xref:System.IAsyncResult.CompletedSynchronously%2A?displayProperty=fullName> 속성에 액세스할 수 있습니다. <xref:System.IAsyncResult.CompletedSynchronously%2A?displayProperty=fullName>의 잘못된 구현으로 현재 <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A?displayProperty=fullName> 메서드 호출의 정의되지 않은 동작이 일어납니다.|<xref:System.IAsyncResult.CompletedSynchronously%2A?displayProperty=fullName> 속성의 구현이 `true`를 잘못 반환한 경우 결과 작업이 완료되지 않습니다.|  
  
<a name="sql"></a>   
## <a name="data"></a>데이터  
  
### <a name="sqlclient"></a>SQLClient  
  
|기능|변경|영향|  
|-------------|------------|------------|  
|[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서 실행되는 관리 코드에서 SQL Server 데이터베이스에 연결하는 기능입니다.|비동기 지원을 추가하도록 기존의 동기 API 코드 경로가 수정되었습니다.|비 IFS Winsock BSP(기본 서비스 공급자) 또는 LSP(계층화된 서비스 공급자)가 있으면 SQL Server에 연결하는 기능을 사용하는 데 방해가 될 수 있습니다. 자세한 내용은 Microsoft 지원 웹 사이트의 [비 IFS LSP가 설치된 경우 SetFileCompletionNotificationModes API 때문에 IO 완료 포트가 제대로 작동하지 않음](http://go.microsoft.com/fwlink/p/?LinkId=256032) 을 참조하세요.|  
|<xref:System.Data.SqlClient.SqlConnection?displayProperty=fullName> 형식|SQL Server 1997 데이터베이스에 대한 연결은 더 이상 지원되지 않습니다.|[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서 실행되는 응용 프로그램은 SQL Server 1997 데이터베이스에 연결할 수 없습니다.|  
|<xref:System.Data.SqlClient.SqlConnection?displayProperty=fullName> 형식|VIA(Virtual Interface Adapter) 프로토콜을 사용하는 SQL Server 데이터베이스에 대한 연결은 더 이상 지원되지 않습니다.|[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서 실행되는 응용 프로그램은 VIA를 사용하여 SQL Server 데이터베이스에 연결할 수 없습니다.|  
|<xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> 형식|열에 데이터를 삽입할 때 <xref:System.Data.SqlClient.SqlBulkCopy>에서는 `VARCHAR` 및 `CHAR` 형식에 대한 기본 인코딩 대신 대상 열의 인코딩을 사용합니다.|이러한 변경을 통해 대상 열에서 기본 인코딩을 사용하지 않는 경우 기본 인코딩을 사용하여 발생하는 데이터 손상의 가능성을 제거합니다. 드물기는 하지만 인코딩에서의 이 변경으로 인해 대상 열에 맞추기에는 너무 큰 데이터가 생성되는 경우, 기존 응용 프로그램에서 <xref:System.Data.SqlClient.SqlException> 예외를 throw할 수 있습니다.|  
|<xref:System.Data.SqlClient?displayProperty=fullName> 데이터 정렬 순서|`sql_variant` 데이터는 데이터베이스 데이터 정렬 대신 `sql_variant` 데이터 정렬을 사용합니다.|이러한 변경을 통해 데이터베이스 데이터 정렬이 `sql_variant` 데이터 정렬과 다른 경우 데이터 손상 가능성을 해결합니다. 손상된 데이터를 사용하는 응용 프로그램은 오류가 발생할 수 있습니다.|  
  
### <a name="entity-framework"></a>Entity Framework  
  
|기능|변경|영향|  
|-------------|------------|------------|  
|<xref:System.Data.Objects.ObjectContext.CreateDatabase%2A?displayProperty=fullName> 메서드에서 만든 로그 파일|<xref:System.Data.Objects.ObjectContext.CreateDatabase%2A> 메서드를 직접 호출하거나 SqlClient 공급자로 Code First를 사용하고 연결 문자열의 `AttachDBFilename` 값을 사용하여 호출하면 *filename*.ldf 대신 *filename*_log.ldf라는 로그 파일이 생성됩니다. 여기서 *filename*은 `AttachDBFilename` 값으로 지정한 파일 이름입니다.|이 변경을 통해 SQL Server 사양에 따라 명명된 로그 파일을 제공하여 디버깅을 개선합니다. 예기치 않은 부작용은 없어야 합니다.|  
|DDL(데이터 정의 언어) API|`AttachDBFilename`이 지정되면 DDL API의 동작은 다음과 같이 변경됩니다.<br /><br /> 연결 문자열에 `Initial Catalog` 값을 지정할 필요는 없습니다. 이전에는 `AttatchDBFilename`과 `Initial Catalog` 둘 다 필요했습니다.<br /><br /> `AttatchDBFilename`과 `Initial Catalog` 둘 다 지정되어 있고 제공된 MDF 파일이 있는 경우 <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A?displayProperty=fullName> 메서드는 `true`를 반환합니다. 이전에는 `false`를 반환했습니다.<br /><br /> `AttatchDBFilename`과 `Initial Catalog` 둘 다 지정되어 있고 제공된 MDF 파일이 있는 경우 <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A?displayProperty=fullName> 메서드를 호출하면 파일이 삭제됩니다.<br /><br /> 존재하지 않는 MDF 및 존재하지 않는 <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A?displayProperty=fullName>로 연결 문자열이 `AttachDBFilename` 값을 지정할 때 `Initial Catalog`가 호출되면, 이 메서드는 <xref:System.InvalidOperationException> 예외를 throw합니다. 이전에는 <xref:System.Data.SqlClient.SqlException> 예외를 throw했습니다.|이러한 변경으로 인해 DDL API를 사용하는 도구와 응용 프로그램을 보다 쉽게 빌드할 수 있습니다. 이러한 변경 사항은 다음 시나리오에서 응용 프로그램 호환성에 영향을 줄 수 있습니다.<br /><br /> `DROP DATABASE`가 <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A?displayProperty=fullName>를 반환할 경우 <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A?displayProperty=fullName>를 호출하는 대신 사용자는 `true` 명령을 직접 실행하는 코드를 작성합니다. 이는 데이터베이스가 연결되지 않았지만 MDF 파일이 있는 경우 기존 코드를 중단시킵니다.<br /><br /> 사용자는 <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A?displayProperty=fullName> 메서드에서 <xref:System.Data.SqlClient.SqlException> 및 MDF 파일이 없을 때 <xref:System.InvalidOperationException> 예외가 아닌 `Initial Catalog` 예외를 throw하도록 기대되는 코드를 작성합니다.|  
|<xref:System.Data.Objects.ObjectContext.CreateDatabase%2A?displayProperty=fullName> 및 <xref:System.Data.Common.DbProviderServices.CreateDatabase%2A?displayProperty=fullName> 메서드|빈 데이터베이스를 만든 후 데이터베이스 개체를 생성하지 못한 경우, 이 메서드는 데이터베이스 생성을 삭제하고 원래 <xref:System.Data.SqlClient.SqlException> 예외를 전달하려고 합니다. 데이터베이스를 삭제하지 못한 경우 이 메서드는 <xref:System.InvalidOperationException> 예외를 throw합니다.|이 변경으로 인해 비어 있거나 사용할 수 없는 데이터베이스 생성을 방지합니다. 제거된 데이터베이스는 이제 원래 <xref:System.Data.SqlClient.SqlException> 예외로 전달되므로 예외 처리가 다소 변경될 수 있습니다.|  
|<xref:System.Data.Objects.ObjectContext.Translate%2A?displayProperty=fullName> 및 <xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%2A?displayProperty=fullName> 메서드|`T`가 열거형 형식인 경우 이 메서드는 데이터베이스에서 데이터를 올바르게 반환합니다.  이전에는 열거형 형식이 지원되지 않아 결과가 항상 0으로 캐스팅되거나 열거형 형식으로 변환되었습니다. <xref:System.UInt16>, <xref:System.UInt32> 및 <xref:System.UInt64>와 같은 Entity Framework에서 지원되지 않는 기본 형식은 그대로 0을 반환하거나 0의 내부 값을 가진 열거형 형식으로 변환됩니다.|열거형에 대한 지원은 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] Entity Framework의 새로운 기능입니다. 그러나 개발자 코드가 0 결과에 종속되는 경우에는 특정 코드에 따라 응용 프로그램 오류가 발생할 수 있습니다.|  
  
### <a name="linq"></a>LINQ  
  
|기능|변경|영향|  
|-------------|------------|------------|  
|<xref:System.Linq.Enumerable.Empty%2A?displayProperty=fullName> 메서드|이 메서드는 새로운 <xref:System.Collections.Generic.IEnumerable%601> 형식을 반환하는 대신 캐시된 내부 인스턴스를 반환합니다.|이 변경을 통해 성능이 개선됩니다. 그러나 <xref:System.Linq.Enumerable.Empty%2A?displayProperty=fullName>에 대한 여러 호출로부터 두 개의 고유한 빈 형식을 얻으려고 하는 코드는 실행되지 않습니다.|  
  
<a name="network"></a>   
## <a name="networking"></a>네트워킹  
  
|기능|변경|영향|  
|-------------|------------|------------|  
|<xref:System.Net.PeerToPeer.Collaboration?displayProperty=fullName> 네임스페이스의 형식 및 멤버|[!INCLUDE[win8](../../../includes/win8-md.md)]에서 지원되지 않는 형식 및 멤버입니다. 호출을 시도하면 <xref:System.PlatformNotSupportedException> 예외가 throw됩니다.|응용 프로그램은 더 이상 이러한 형식과 멤버를 [!INCLUDE[win8](../../../includes/win8-md.md)]에서 사용할 수 없습니다.|  
|<xref:System.Net.Mail.MailMessage> 개체 Serialization 및 Deserialization|.NET Framework 4.5에서는 메일 메시지에 ASCII가 아닌 문자를 포함할 수 있습니다. .NET Framework 4에서는 ASCII 문자만 지원됩니다.|ASCII가 아닌 문자를 포함하고 .NET Framework 4.5 하에서 serialize되는 <xref:System.Net.Mail.MailMessage> 개체는 .NET Framework 4 하에서 deserialize될 수 없습니다.|  
  
<a name="Printing"></a>   
## <a name="printing"></a>인쇄  
  
|기능|변경|영향|  
|-------------|------------|------------|  
|<xref:System.Printing.PrintSystemJobInfo.JobStream%2A?displayProperty=fullName>|이 속성은 인쇄 작업 스트림을 노출하고 사용자가 이 스트림을 작성하여 기본 운영 체제 인쇄 구성 요소로 원시 데이터를 보낼 수 있도록 허용합니다.<br /><br /> Windows 8 이후 버전 Windows 운영 체제의 .NET Framework 4.5부터 이 스트림에 작성되는 데이터는 패키지 스트림과 같은 XPS 형식이어야 합니다.|인쇄 내용을 출력하려면 다음 중 하나를 수행할 수 있습니다.<br /><br /> <xref:System.Windows.Xps.XpsDocumentWriter> 클래스를 사용하여 인쇄 내용을 출력합니다. 이는 권장되는 대안입니다.<br /><br /> <xref:System.Printing.PrintSystemJobInfo.JobStream%2A?displayProperty=fullName> 속성에서 반환된 스트림으로 전송된 데이터가 패키지 스트림과 같은 XPS 형식인지 확인합니다.|  
  
<a name="serialize"></a>   
## <a name="serialization"></a>Serialization  
  
|기능|변경|영향|  
|-------------|------------|------------|  
|<xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용한 Serialization|WCF 4.5에서는 C# 컴파일러에서 해당 종속성을 제거하기 위해 <xref:System.Xml.Serialization.XmlSerializer> 클래스가 최적화되었습니다. 이 변경은 콜드 시작 시나리오의 성능을 크게 향상시킵니다.|이 변경으로 인해 WCF 4에서 컴파일되었지만 WCF 4.5에 대해 실행되는 XML serialization 코드에서 문제가 발생할 수 있습니다. WCF 4.5에서 기존 XML serialization 코드 실행 중 문제가 발생하는 경우 다음 구성 요소를 사용하여 WCF 4의 XmlSerializer 동작으로 되돌립니다.<br /><br /> `<configuration>    <system.xml.serialization>    <xmlSerializer useLegacySerializerGeneration="true"/>    </system.xml.serialization> </configuration>`|  
|<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> 클래스를 사용한 serialization 및 deserialization|<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>를 사용한 serialization은 여러 .NET Framework 버전 간에 서로 다를 수 있는 개체 내부 상태를 인코드할 수 있습니다.  차이가 있기 때문에 한 버전의 .NET Framework에서 deserialize된 콘텐츠가 다른 버전에서는 deserialize되지 않을 수 있습니다.|<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> 클래스는 버전 간 호환성이 보장되지 않으므로 대신 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> 클래스와 <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> 클래스를 사용합니다.|  
  
<a name="tools"></a>   
## <a name="tools-and-resources"></a>도구 및 리소스  
  
|기능|변경|영향|  
|-------------|------------|------------|  
|MSBuild|명령 프롬프트에서 MSBuild를 실행하면 특정 프로젝트의 빌드를 사용하지 않도록 설정하는 솔루션 구성 파일을 적용합니다.|MSBuild는 Visual Studio에서 호출되는 경우와 명령 프롬프트에서 실행되는 경우 동일하게 동작합니다. 개별 솔루션을 만들거나 솔루션에서 프로젝트를 제거하여 솔루션에 프로젝트의 하위 집합을 빌드할 필요가 없습니다.|  
|MSBuild|MSBuild 프로젝트 파일의 `TreatAsLocalProperty` 속성은 전역 수준에서 재정의되는 `OutDir` 속성을 포함하는 특정 속성을 방지합니다.|`OutDir`이 MS.Common.Targets 파일을 가져온 다음 재정의된 전역 속성인 경우 `OutDir` 속성을 재정의하면 중단될 수 있습니다.|  
|Windows 오류 보고: Watson 버킷|관리되는 충돌은 다양한 기준에 따라 범주로 그룹화되며, 그 기준 중 하나가 어셈블리 버전이었습니다. [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서는 어셈블리 버전 대신 파일 버전이 사용되었습니다.|주요 릴리스 사이에서만 어셈블리 버전이 변경되기 때문에, 어셈블리 버전 대신 파일 버전을 범주로 사용하면 관리되는 충돌과 연관이 있는 어셈블리의 특정 버전을 확인할 수 있습니다.|  
|MSBuild|<xref:Microsoft.Build.Evaluation.ProjectCollection?displayProperty=fullName> 컬렉션의 프로젝트 데이터는 가비지 수집기를 통해 자동으로 회수되지 않습니다.|프로젝트를 <xref:Microsoft.Build.Evaluation.ProjectCollection> 컬렉션에 명시적으로 로드한 경우 컬렉션의 각 멤버에 대해 <xref:Microsoft.Build.Evaluation.ProjectCollection.UnloadProject%28Microsoft.Build.Evaluation.Project%29> 메서드를 호출해야 합니다.|  
  
<a name="asp"></a>   
## <a name="aspnet"></a>ASP.NET  
  
|기능|변경|영향|  
|-------------|------------|------------|  
|ASP.NET IIS 등록 도구(aspnet_regiis.exe)|[!INCLUDE[win8](../../../includes/win8-md.md)]에서는 ASP.NET을 설치 및 제거하기 위한 `–i` 및 `–u` 옵션이 지원되지 않습니다.|IIS 8이 포함된 ASP.NET 4.5를 설치하거나 제거하려면 **Windows 기능 사용/사용 안 함** 대화 상자, 서버 관리 도구 또는 `dism.exe` 명령줄 도구를 사용합니다.|  
|<xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=fullName> 컨트롤|<xref:System.Web.UI.Page.LoadComplete?displayProperty=fullName> 이벤트로 인해 더 이상 <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=fullName> 컨트롤에서 매개 변수 생성/업데이트/삭제를 위해 변경 내용에 대한 데이터 바인딩을 호출하지 않습니다.|이러한 변경으로 인해 데이터베이스에 대한 불필요한 이동이 제거되고 컨트롤 값이 다시 설정되는 것을 방지하며 <xref:System.Web.UI.WebControls.SqlDataSource> 및 <xref:System.Web.UI.WebControls.ObjectDataSource> 같은 다른 데이터 컨트롤과 일관된 동작을 발생시킵니다. 이러한 변경으로 인해 드물게 응용 프로그램에서 <xref:System.Web.UI.Page.LoadComplete?displayProperty=fullName> 이벤트의 데이터 바인딩 호출을 사용하는 경우 다른 동작이 발생합니다.|  
|<xref:System.Net.WebUtility.HtmlDecode%2A?displayProperty=fullName>, <xref:System.Net.WebUtility.UrlDecode%2A?displayProperty=fullName> 및 [System.Web.Helpers.Json.Decode](https://msdn.microsoft.com/library/system.web.helpers.json.decode.aspx) 메서드|기본적으로 디코딩 메서드는 더 이상 잘못된 입력 시퀀스를 잘못된 UTF-16 문자열로 디코딩하지 않습니다. 대신, 원래 입력을 반환합니다.|문자열에 UTF-16 데이터 대신 이진 데이터를 저장하는 경우에만 디코더 출력에서의 변경 사항이 문제가 되어야 합니다. 이러한 동작을 명시적으로 제어하려면 [\<appSettings>](http://msdn.microsoft.com/en-us/0d65a3f1-c522-423d-89b6-44921b6daebb) 요소의 `aspnet:AllowRelaxedUnicodeDecoding` 특성을 `true`로 설정하여 레거시 동작을 사용하도록 설정하거나 `false`로 설정하여 현재 동작을 사용하도록 설정합니다.|  
|<xref:System.Net.WebUtility.HtmlEncode%2A?displayProperty=fullName> 메서드|[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]를 대상으로 하는 응용 프로그램의 경우 BMP(기본적인 다국어 문자표) 외의 문자는 <xref:System.Net.WebUtility.HtmlDecode%2A?displayProperty=fullName> 메서드에 전달될 때 올바르게 라운드트립합니다.|이 변경은 현재 응용 프로그램에 영향을 주면 안 됩니다. 원래 동작으로 복원하려면 [\<httpRuntime>](http://msdn.microsoft.com/library/e1f13641\(v=vs.100\).aspx) 요소의 `targetFramework` 특성을 "4.5" 이외의 문자열로 설정합니다. `unicodeEncodingConformance` 구성 요소의 `unicodeDecodingConformance` 및 `<webUtility>` 특성을 설정하여 대상 버전의 .NET Framework에 관계없이 이 동작을 제어할 수도 있습니다.|  
|<xref:System.Web.HttpRequest.ContentEncoding%2A?displayProperty=fullName> 속성|UTF-7 인코딩은 허용되지 않습니다.|경우에 따라 UTF-7 수신 데이터에 종속되는 응용 프로그램 데이터가 제대로 디코딩되지 않습니다. 이는 드문 경우지만 [\<appSettings>](http://msdn.microsoft.com/en-us/0d65a3f1-c522-423d-89b6-44921b6daebb) 요소의 `aspnet:AllowUtf7RequestContentEncoding` 특성을 사용하여 레거시 동작을 복원할 수 있습니다.|  
|<xref:System.Web.HttpUtility.JavaScriptStringEncode%2A?displayProperty=fullName>|[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]부터 이 메서드는 앰퍼샌드(&) 문자를 이스케이프합니다.|응용 프로그램이 이 메서드의 이전 동작에 종속되는 경우 `aspnet:JavaScriptDoNotEncodeAmpersand` 설정을 구성 파일에 있는 [ASP.NET appSettings 요소](http://msdn.microsoft.com/en-us/bb60e711-0669-4118-a54d-8dd71e009a00)에 추가할 수 있습니다.|  
|<xref:System.Web.Security.MachineKey.Encode%2A?displayProperty=fullName> 및 <xref:System.Web.Security.MachineKey.Decode%2A?displayProperty=fullName> 메서드|이러한 메서드는 이제 사용되지 않습니다.|이러한 메서드를 호출하는 코드를 컴파일하면 컴파일러 경고가 생성됩니다. <xref:System.Web.Security.MachineKey.Protect%2A?displayProperty=fullName> 및 <xref:System.Web.Security.MachineKey.Unprotect%2A?displayProperty=fullName>를 대신 사용하는 것이 좋습니다.|  
  
<a name="ClickOnce"></a>   
## <a name="clickonce"></a>ClickOnce  
  
|기능|변경|영향|  
|-------------|------------|------------|  
|SHA-256 코드 서명 인증서를 사용하는 ClickOnce로 게시된 앱|실행 파일이 SHA256으로 서명됩니다. 이전에는 코드 서명 인증서가 SHA-1 또는 SHA-256인지에 관계없이 SHA1로 서명되었습니다. 적용 대상:<br /><br /> Visual Studio 2012 이상으로 빌드된 모든 응용 프로그램<br /><br /> .NET Framework 4.5가 있는 시스템에서 Visual Studio 2010 또는 이전 버전으로 빌드된 응용 프로그램<br /><br /> 또한 .NET Framework 4.5 이상이 있는 경우 컴파일 시의 대상 .NET Framework 버전에 관계없이 ClickOnce 매니페스트도 SHA-256 인증서에 대해 SHA-256으로 서명됩니다.|ClickOnce 실행 파일의 서명 변경 내용은 Windows Server 2003 시스템에만 영향을 줍니다. [KB 938397](http://support.microsoft.com/kb/938397)을 설치해야 합니다.<br /><br /> 앱이 .NET Framework 4 또는 이전 버전을 대상으로 하는 경우에도 SHA-256으로 매니페스트에 서명하는 변경 내용으로 인해 .NET Framework 4.5 이상 버전에서 런타임 종속성이 발생합니다. 이 문제가 Visual Studio 2013 업데이트 3 및 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]에서 해결되었습니다. [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 해결 방법은 [런타임 변경 내용](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)을 참조하세요.|  
  
<a name="mef"></a>   
## <a name="managed-extensibility-framework-mef"></a>MEF(Managed Extensibility Framework)  
  
|기능|변경|영향|  
|-------------|------------|------------|  
|<xref:System.ComponentModel.Composition.Primitives.ComposablePartCatalog?displayProperty=fullName> 및 그 파생 클래스|[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]부터 MEF 카탈로그는 <xref:System.Collections.IEnumerable>을 구현하므로 더 이상 serializer(<xref:System.Xml.Serialization.XmlSerializer> 개체)를 만드는 데 사용할 수 없습니다.|MEF 카탈로그를 serialize하려고 하면 예외가 throw됩니다.|  
  
<a name="web"></a>   
## <a name="web-applications"></a>웹 응용 프로그램  
  
|기능|변경|영향|  
|-------------|------------|------------|  
|.NET Framework 1.1 및 2.0에서의 관리되는 브라우저 호스팅 컨트롤|이러한 컨트롤의 호스팅은 Internet Explorer에서 차단됩니다.|Internet Explorer에서는 관리되는 브라우저 호스팅 컨트롤을 사용하는 응용 프로그램을 시작하지 못합니다. x86 시스템 및 x64 시스템의 32비트 프로세스의 경우 레지스트리 하위 키 HKLM/SOFTWARE/MICROSOFT/.NETFramework의 EnableIEHosting 값을 1로 설정하고, x64 시스템의 64비트 프로세스의 경우 레지스트리 하위 키 HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework의 EnableIEHosting 값을 1로 설정하여 이전 동작을 복원할 수 있습니다.|  
  
<a name="wcf"></a>   
## <a name="windows-communication-foundation-wcf"></a>WCF(Windows Communication Foundation)  
 다음 응용 프로그램 호환성 문제 외에 [Serialization](#serialize) 섹션의 serialization 관련 문제를 참조하세요.  
  
|기능|변경|영향|  
|-------------|------------|------------|  
|`maxRequestLength`(ASP.NET에서) 또는 `maxReceivedMessageSize`(WCF에서)를 초과하는 IIS(인터넷 정보 서비스) 또는 ASP.NET Development Server에서 호스팅된 WCF 웹 서비스의 메시지|HTTP 상태 코드는 400(잘못된 요청)에서 413(요청 엔터티가 너무 큼)으로 변경되었으며 `maxRequestLength` 또는 `maxReceivedMessageSize` 설정을 초과하는 메시지는 <xref:System.ServiceModel.ProtocolException> 예외를 throw합니다. 이는 전송 모드가 <xref:System.ServiceModel.TransferMode>인 경우를 포함합니다.|이러한 변경으로 인해 메시지 길이가 ASP.NET 또는 WCF에서 허용한 한계를 초과하는 경우 쉽게 디버깅할 수 있습니다.<br /><br /> 400 HTTP 상태 코드를 기반으로 처리하는 모든 코드를 수정해야 합니다.|  
|OData URL의 `Replace`|OData Url의 `Replace` 메서드는 기본적으로 비활성화되어 있습니다.|OData `Replace`가 비활성화된 경우(현재 기본값) 사용자 요청은 예외를 throw하고 요청이 수행되지 않습니다.|  
|<xref:System.ServiceModel.Web.WebServiceHost?displayProperty=fullName>|응용 프로그램 코드를 통해 명시적 끝점을 추가한 경우에는 <xref:System.ServiceModel.Web.WebServiceHost?displayProperty=fullName> 개체가 더 이상 기본 끝점을 추가하지 않습니다.|더 이상 코드를 추가할 수 없도록 기본값이 설정된 끝점에 클라이언트 응용 프로그램을 연결하려고 하면 HTTP 오류가 발생합니다.|  
  
<a name="winForms"></a>   
## <a name="windows-forms"></a>Windows Forms  
  
|기능|변경|영향|  
|-------------|------------|------------|  
|System.Drawing.dll|어셈블리의 `CheckForOverflowUnderflow` 속성은 `true`로 설정됩니다.|이전에 오버플로가 발생했을 때는 결과가 자동으로 잘렸습니다. 이제 <xref:System.OverflowException> 예외가 throw됩니다.|  
|<xref:System.Drawing.Imaging.EncoderParameter.%23ctor%28System.Drawing.Imaging.Encoder%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName> 생성자|이 생성자는 사용되지 않습니다.|이 생성자는 64비트 시스템에서 작동하지 않습니다. <xref:System.Drawing.Imaging.EncoderParameter.%23ctor%28System.Drawing.Imaging.Encoder%2CSystem.Int32%2CSystem.Drawing.Imaging.EncoderParameterValueType%2CSystem.IntPtr%29?displayProperty=fullName> 생성자를 대신 사용하십시오.|  
  
<a name="wpf"></a>   
## <a name="windows-presentation-foundation-wpf"></a>WPF(Windows Presentation Foundation)  
 다음 응용 프로그램 호환성 문제 외에 [Serialization](#serialize) 섹션의 serialization 관련 문제를 참조하세요.  
  
|기능|변경|영향|  
|-------------|------------|------------|  
|<xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit%2A?displayProperty=fullName> 속성|<xref:System.Windows.Controls.TextBox> 및 <xref:System.Windows.Controls.RichTextBox> 클래스의 경우 실행 취소 작업의 최대 수에 대한 기본 제한이 -1(제한 없음)에서 100으로 변경되었습니다.|이 변경은 부정적인 영향을 주어서는 안 됩니다. 그러나 컨트롤을 인스턴스화한 후 <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit%2A> 속성을 명시적으로 설정할 수 있습니다.|  
|<xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> 열거형|<xref:System.Windows.Controls.PageRangeSelection> 및 <xref:System.Windows.Controls.PageRangeSelection> 멤버가 열거형에 추가되었습니다.|이 변경은 기존 응용 프로그램에 영향을 주어서는 안 됩니다. 기본값은 이 열거형을 사용하는 기존 멤버의 경우 <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>입니다.|  
|<xref:System.Windows.DataTemplate> 요소|<xref:System.Windows.DataTemplate> 요소는 이제 UIA(UI 자동화) 트리의 컨트롤 뷰에 나타납니다.|이러한 변경으로 인해 액세스 가능성이 개선됩니다. 그러나 인접한 요소에 위치한 이전의 UIA 트리 구조에 종속적인 테스트 도구에 영향을 줍니다.|  
|<xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=fullName> 속성과 해당 속성이 바인딩된 속성의 동기화|경우에 따라 <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=fullName> 속성은 데이터 바인딩 쓰기 작업 중 속성이 수정되면 데이터 바인딩된 속성 값의 이전 값을 반영합니다.|이는 부정적인 영향을 주어서는 안 됩니다. 그러나 <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty%2A?displayProperty=fullName> 속성을 `false`로 설정하여 이전 동작을 복원할 수 있습니다.|  
|<xref:System.Windows.Controls.TextBox?displayProperty=fullName> 속성|<xref:System.Windows.Controls.TextBox?displayProperty=fullName> 컨트롤이 비활성화되면 상자 안의 선택된 텍스트는 텍스트 상자가 활성화되었을 때와는 다른 색으로 표시됩니다.|<xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported%2A?displayProperty=fullName> 속성을 `false`로 설정하여 이전 동작을 복원할 수 있습니다.|  
|<xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A?displayProperty=fullName>|<xref:System.Windows.Controls.Primitives.MultiSelector.CanSelectMultipleItems%2A>가 `true`로 설정된 <xref:System.Windows.Controls.Primitives.MultiSelector>에서 파생된 컨트롤의 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A?displayProperty=fullName> 컬렉션에 중복이 있으면, 중복된 항목은 두 번 이상 표시됩니다. 이러한 항목을 데이터 소스에서 제거하면(예: `Items.Clear`를 호출하여) <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A?displayProperty=fullName> 컬렉션에서 제거할 수 없으며, 첫 번째 인스턴스만 제거됩니다.<br /><br /> <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A?displayProperty=fullName> 컬렉션을 뒤이어 사용하면(예: `SelectedItems.Clear`에 대한 호출), <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A?displayProperty=fullName> 컬렉션이 더 이상 데이터 소스에 없는 항목을 포함하기 때문에, <xref:System.ArgumentException>과 같은 문제가 발생할 수 있습니다.|이 문제는 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]에서 해결되었습니다. <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A?displayProperty=fullName> 컬렉션에 중복 항목이 있으면, 데이터 소스에서 제거하고, <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A?displayProperty=fullName> 컬렉션으로 계속 작업하고 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]로 업그레이드합니다.|  
|<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy%2A?displayProperty=fullName>|[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]에서 이 메서드는 현재 인스턴스에 대한 참조를 반환합니다. [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서는 새 인스턴스를 반환합니다.|실행 중인 스레드를 나타내는 동일한 참조가 올바른 컨텍스트에 있다고 가정하는 코드가 이제 제대로 실행됩니다. 그러나, 이 변경으로 인해 <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy%2A?displayProperty=fullName>를 호출하는 코드를 테스트해야 합니다.|  
|<xref:System.Windows.Interop.HwndSource.AddHook%2A?displayProperty=fullName> 메서드를 호출하여 추가한 처리기를 사용하여 `WM_POWERBROADCAST` 메시지 모니터링|창에서 해당 핸들을 `WM_POWERBROADCAST` RegisterPowerSettingNotification [함수로 전달하여](https://msdn.microsoft.com/library/windows/desktop/aa373196.aspx) 알림을 명시적으로 등록해야 합니다. [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]를 통해 WPF가 모든 창에 대해 자동으로 이 작업을 수행했습니다. [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]부터는 WPF가 자동으로 하나의 특별한 창을 등록하고 대부분의 앱 창을 자동으로 등록하지 않습니다.|`WM_POWERBROADCAST` 알림을 처리하는 코드가 실행되지 않습니다.<br /><br /> 계속 `WM_POWERBROADCAST` 알림을 받으려면 [RegisterPowerSettingNotification](https://msdn.microsoft.com/library/windows/desktop/aa373196.aspx) 함수를 호출하여 `WM_POWERBROADCAST` 알림을 위한 WPF 창(일반적으로 주 응용 프로그램 창)을 등록합니다. C#으로 개발하는 WPF 앱에서 이 작업을 수행하려면 프로젝트 속성 **빌드** 탭에서 **안전하지 않은 코드 허용** 상자도 선택해야 합니다.<br /><br /> 또한 응용 프로그램이 종료될 때까지 지속되지 않는 창을 등록하는 경우 [UnregisterPowerSettingNotification](https://msdn.microsoft.com/library/windows/desktop/aa373237.aspx) 함수를 호출하고 `HPOWERNOTIFY` RegisterPowerSettingNotification [함수 호출에서 반환한](https://msdn.microsoft.com/library/windows/desktop/aa373196.aspx) 핸들을 전달하여 등록 취소해야 합니다.|  
  
<a name="wwf"></a>   
## <a name="windows-workflow-foundation-wf"></a>Windows WF(Workflow Foundation)  
  
|기능|변경|영향|  
|-------------|------------|------------|  
|System.Activities.dll security|이 어셈블리는 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 특성으로 표시되어 있습니다.|파생 클래스는 <xref:System.Security.SecurityCriticalAttribute>로 표시할 수 없습니다. 이전에는 파생된 형식을 <xref:System.Security.SecurityCriticalAttribute>로 표시해야 했습니다. 그러나 이 변경은 실제로 영향을 주어서는 안 됩니다.|  
|WF 3.0 형식 및 멤버|WF 3.0의 형식과 멤버는 이제 사용되지 않음으로 표시됩니다.|WF 3.0 형식 또는 멤버를 사용하는 소스 코드를 컴파일하려고 하면 컴파일러 오류가 발생합니다. <xref:System.Activities> 네임스페이스에서 WF 4 형식과 멤버를 사용해야 합니다.|  
|<xref:System.Activities.Presentation.DragDropHelper?displayProperty=fullName> 클래스|<xref:System.Activities.Presentation.DragDropHelper> 클래스는 여러 개체에서 끌어서 놓기 작업을 지원하는 새 메서드를 포함합니다. 단일 개체 끌기를 지원하는 기존의 끌어서 놓기 방법은 사용되지 않습니다. 자세한 내용은 [클래스 라이브러리의 사용되지 않는 기능](../../../docs/framework/whats-new/whats-obsolete.md)을 참조하세요.|이전 메서드는 더 이상 사용되지 않지만 컴파일러와 공용 언어 런타임 모두에서 계속 지원됩니다. 그러나 새 메서드는 더욱 향상된 기능을 제공합니다. 기존 메서드 일부에 대해 권장하는 대체 항목은 다음과 같습니다.<br /><br /> <xref:System.Activities.Presentation.DragDropHelper.DoDragMove%28System.Activities.Presentation.WorkflowViewElement%2CSystem.Windows.Point%29?displayProperty=fullName> 대신 <xref:System.Activities.Presentation.DragDropHelper.DoDragMove%28System.Activities.Presentation.WorkflowViewElement%2CSystem.Windows.Point%29?displayProperty=fullName>를 사용합니다.<br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView%28System.Activities.Presentation.WorkflowViewElement%29> 대신 <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView%28System.Windows.DragEventArgs%29>를 사용합니다.<br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItems%28System.Windows.DragEventArgs%29> 대신 <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem%28System.Windows.DragEventArgs%29>를 사용합니다.<br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObjects%28System.Windows.DependencyObject%2CSystem.Windows.DragEventArgs%2CSystem.Activities.Presentation.EditingContext%29> 대신 <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject%28System.Windows.DependencyObject%2CSystem.Windows.DragEventArgs%2CSystem.Activities.Presentation.EditingContext%29>를 사용합니다.|  
|<xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=fullName> 메서드에 대한 호출의 오버로드 확인|[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서는 <xref:System.Action?displayProperty=fullName> 형식의 매개 변수를 포함하는 새 오버로드를 추가합니다. 기존 코드를 다시 컴파일하면 컴파일러는 <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=fullName> 매개 변수를 가진 <xref:System.Delegate> 메서드에 대한 호출로서 <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=fullName> 매개 변수를 갖는 <xref:System.Action?displayProperty=fullName> 메서드에 대한 호출을 해결할 수 있습니다.|<xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=fullName> 매개 변수를 가진 <xref:System.Delegate> 오버로드를 호출함으로써 해결된 <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=fullName> 매개 변수를 가진 <xref:System.Action?displayProperty=fullName> 오버로드를 호출하는 경우, 다음과 같은 동작 차이가 발생할 수 있습니다.<br /><br /> 예외가 발생하는 경우 <xref:System.Windows.Threading.Dispatcher.UnhandledExceptionFilter?displayProperty=fullName> 및 <xref:System.Windows.Threading.Dispatcher.UnhandledException?displayProperty=fullName> 이벤트가 발생하지 않습니다. 대신 예외는 <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> 이벤트에 의해 처리됩니다.<br /><br /> <xref:System.Windows.Threading.DispatcherOperation.Result%2A?displayProperty=fullName>와 같은 일부 멤버에 대한 호출은 작업이 완료될 때까지 차단됩니다.|  
|<xref:System.Activities.Expressions.Literal%601?displayProperty=fullName> 클래스|연결된 <xref:System.Windows.Markup.ValueSerializer> 개체는 <xref:System.DateTime> 및 <xref:System.DateTimeOffset> 구성 요소가 0이 아니고(`Second` 값의 경우) `Millisecond` 속성이 <xref:System.DateTime>가 아닌 <xref:System.DateTime.Kind%2A?displayProperty=fullName> 또는 <xref:System.DateTimeKind> 개체를 문자열 대신에 속성 요소 구문으로 변환합니다.|이 변경은 <xref:System.DateTime> 및 <xref:System.DateTimeOffset> 값이 라운드트립되는 것을 허용합니다. 입력 XAML이 특성 구문에 있다고 가정하는 사용자 지정 XAML 파서가 올바르게 작동하지 않습니다.|  
  
<a name="xml"></a>   
## <a name="xml-xslt"></a>XML, XSLT  
  
|기능|변경|영향|  
|-------------|------------|------------|  
|`XDocument.Validate` 메서드|<xref:System.Xml.Linq.LoadOptions?displayProperty=fullName> 값을 <xref:System.Xml.Linq.XDocument.Load%2A> 메서드에 전달하고 유효성 검사 오류가 발생한 경우 <xref:System.Xml.Schema.XmlSchemaException.LineNumber%2A?displayProperty=fullName> 및 <xref:System.Xml.Schema.XmlSchemaException.LinePosition%2A?displayProperty=fullName> 속성은 이제 줄 정보를 포함합니다.|<xref:System.Xml.Schema.XmlSchemaException.LineNumber%2A?displayProperty=fullName> 및 <xref:System.Xml.Schema.XmlSchemaException.LinePosition%2A?displayProperty=fullName> 속성 값에 종속되는 예외 처리 코드는 더 이상 작동하지 않습니다.|  
|<xref:System.Xml.XmlTextReader?displayProperty=fullName>를 사용하여 XML 파일 로드|DTD 엔터티 확장은 10,000,000자로 제한됩니다.|DTD 엔터티 확장 없이 또는 제한된 DTD 엔터티 확장으로 XML 파일을 로드해도 영향을 받지 않습니다. 이제 파일에 10,000,000자를 초과하는 문자로 확장되는 DTD 엔터티가 있으면 로드하지 못하고 예외를 throw합니다.|  
|<xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=fullName> 클래스에 대한 다음 버전과의 호환성 모드|[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]에서 XSLT 1.0 다음 버전과의 호환성에 다음과 같은 문제가 있었습니다.<br /><br /> 버전이 2.0으로 설정되고 인식할 수 없는 XSLT 1.0 구문에서 파서가 발생하면 스타일시트를 로드하지 못했습니다.<br /><br /> 스타일시트 버전이 1.1로 설정된 경우 `xsl:sort` 구문이 데이터를 정렬하지 못했습니다.<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서 이러한 문제가 해결되었고 XSLT 1.0의 다음 버전과의 호환성 모드는 제대로 작동합니다.|XSLT 1.0 다음 버전과의 호환성 모드가 이제 이전처럼 작동합니다.|  
|XSLT 파일이 너무 복잡할 때의 예외 메시지|[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서 XSLT 파일이 너무 복잡할 경우 오류 메시지의 텍스트는 "스타일시트가 너무 복잡합니다."입니다. 이전 버전에서 오류 메시지는 "XSLT 컴파일 오류입니다."였습니다.|오류 메시지 텍스트에 종속되어 있는 응용 프로그램 코드는 더 이상 작동하지 않습니다. 그러나 예외 형식은 동일하게 유지되므로 이 변경은 실제 영향을 미쳐서는 안 됩니다.|  
|xsd:anyURI에 대한 XML 스키마 유효성 검사|[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서 XML 스키마 유효성 검사는 더욱 엄격하게 적용됩니다. mailto 프로토콜과 같이 URI의 유효성을 검사하기 위해 xsd:anyURI을 사용하는 경우 URI에 공백이 있으면 유효성 검사에 실패합니다. 이전 버전의 .NET Framework에서는 유효성 검사에 성공했습니다.|해당 변경 내용은 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]를 대상으로 하는 응용 프로그램에만 영향을 줍니다.|  
  
## <a name="see-also"></a>참고 항목  
 [클래스 라이브러리의 사용되지 않는 기능](../../../docs/framework/whats-new/whats-obsolete.md)   
 [새로운 기능](../../../docs/framework/whats-new/index.md)   
 [응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility.md)   
 [4.5.1의 응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)   
 [4.5.2의 응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)
