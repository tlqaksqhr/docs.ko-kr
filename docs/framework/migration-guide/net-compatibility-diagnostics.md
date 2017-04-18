---
title: ".NET 호환성에 대 한 진단 유틸리티 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5e481270-b62a-4cb4-8dda-5b4c5b59d61d
caps.latest.revision: 7
author: "twsouthwick"
ms.author: "tasou"
manager: "wpickett"
caps.handback.revision: 7
---
# .NET 호환성에 대 한 진단 유틸리티
.NET 호환성 진단에는.NET Framework 버전 간에 응용 프로그램 호환성 문제를 식별할 수 있도록 Roslyn 전원이 분석기는 됩니다. 이 목록 모든 분석기를 사용할 수 있지만 모든 특정 마이그레이션에 하위 집합에만 적용 됩니다 포함 됩니다. 문제는 예정 된 마이그레이션에 대 한 적용 되며 해당 노출할만 분석기에서 결정 됩니다. 문제에 영향을 버전별 분할에 대 한 참조 하십시오: [응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility.md)합니다.  
  
 각 문제에는 다음 정보가 포함 됩니다.  
  
-   이전 버전에서 변경 된 내용을 설명입니다.  
  
-   변경 내용을 고객에 미치는 영향 및 해결 방법을 버전 간 호환성을 유지 하기 위해 사용할 수 있는지에 대 한 설명을 있습니다.  
  
-   얼마나 중요 한 변경 내용은 평가 합니다. 응용 프로그램 호환성 문제는 다음과 같이 분류 됩니다.  
  
    |||  
    |-|-|  
    |주요함|다 수의 앱에 영향을 주거나 코드를 대폭 수정 해야 하는 중요 한 변경 합니다.|  
    |사소함|소수의 앱에 영향을 미치는 주거나 코드를 약간만 수정 해야 하는 변경 합니다.|  
    |특별한 경우|매우 구체적인, 드문 시나리오의 앱에 영향을 주는 변경 합니다.|  
    |투명|응용 프로그램의 개발자나 사용자에 게 뚜렷한 영향으로 변경 합니다.|  
  
-   버전 변경 프레임 워크에 처음 나타날 때를 나타냅니다. 일부 변경 내용이 사라집니다 하 고 있는 표시 됩니다.  
  
-   변경 유형:  
  
    |||  
    |-|-|  
    |대상 변경|새 버전의.NET Framework를 대상으로 컴파일되는 앱에 변경 내용이 적용 됩니다.|  
    |런타임|이전 버전의.NET Framework를 대상으로 하지만 이후 버전에서 실행 하는 기존 앱에 변경 내용이 적용 됩니다.|  
  
-   영향을 받는 API 있는 경우입니다.  
  
-   사용 가능한 진단의 Id  
  
<a name="diagnostic1"></a>   
## <a name="1-soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a>1: SoapFormatter 해시 테이블을 역직렬화 할 수 없습니다 및 순서가 지정 된 유사한 컬렉션 개체  
  
|||  
|-|-|  
|세부 정보|SoapFormatter 한.NET Framework 버전은 다른 버전에서 성공적으로 deserialize 할 개체에 serialize 되도록 하는 것을 보장 하지 않습니다. 특히, 일부 순서가 지정 된 컬렉션 (예: Hashtable) 추가 4.0 및 4.5 사이의 멤버는.NET 4.5 serialzied 마치.NET 4.0과 함께 이러한 형식의 개체 역직렬화 할 수 없습니다. Note 경우 serialize 된 데이터는 직렬화와 같은.NET Framework 버전을 사용 하 여 역직렬화에서 없는 문제가 발생 합니다.|  
|제안 해결 방법|SoapFormatter serialization BinaryFormatter serialization 또는.NET Framework 변경 내용에 복원 력이 있어야 NetDataContractSerialization로 대체 해야 합니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize%28System.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize%28System.IO.Stream%2CSystem.Runtime.Remoting.Messaging.HeaderHandler%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize%28System.IO.Stream%2CSystem.Object%29?displayProperty=fullName><br /><br /> [SoapFormatter.Serialize (스트림, 개체, 헤더\<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize%28System.IO.Stream%2CSystem.Object%2CSystem.Runtime.Remoting.Messaging.Header%5B%5D%29?displayProperty=fullName>|  
|분석기|CD0001B<br /><br /> CD0001A|  
  
<a name="diagnostic3"></a>   
## <a name="3-wpf-datatemplate-elements-are-now-visible-to-uia"></a>3: WPF DataTemplate 요소 UIA에 표시 됩니다.  
  
|||  
|-|-|  
|세부 정보|이전에 DataTemplate 요소 UI 자동화에 표시 되지 않았습니다. UI 자동화 4.5 부터는 이러한 요소를 감지 합니다. 이 대부분의 경우에 유용 하지만 DataTemplate 요소를 포함 하지 않는 UIA 트리에 의존 하는 테스트를 중단할 수 있습니다.|  
|제안 해결 방법|UI Auomation 테스트가이 앱에 필요할 수에 대 한 이전에 보이지 않는 DataTemplate 요소를 포함 하 여 이제 UIA 트리를 고려 하는 업데이트. 예를 들어 일부 요소가 서로 옆에 있는 수를 예상 하는 테스트 이제 사이 이전에 보이지 않는 UIA 요소를 예상 해야 합니다. 또는 테스트 UIA 요소 할 수에 대 한 특정 개수 또는 인덱스를 사용 하는 새 값으로 업데이트 합니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Windows.DataTemplate.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Windows.DataTemplate.%23ctor%28System.Object%29?displayProperty=fullName>|  
|분석기|CD0003|  
  
<a name="diagnostic4"></a>   
## <a name="4-wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a>4: WPF 텍스트 상자가 텍스트 텍스트 상자를 사용 하지 않으면 다른 색 표시  
  
|||  
|-|-|  
|세부 정보|.NET 4.5에서는 WPF 텍스트 상자 컨트롤을 사용 하지 않으면 (것으로 지정 되지 않은 포커스) 상자 안의 선택 된 텍스트 컨트롤이 활성화 된 색과 다르게 표시 됩니다.|  
|제안 해결 방법|이전 (.NET 4.0) 동작을 설정 하 여 복원 될 수 있습니다는 [FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported](https://msdn.microsoft.com/en-us/library/system.windows.frameworkcompatibilitypreferences.areinactiveselectionhighlightbrushkeyssupported\(v=vs.110\).aspx) 속성을 false로 합니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Windows.Controls.TextBox?displayProperty=fullName>|  
|분석기|CD0004|  
  
<a name="diagnostic5"></a>   
## <a name="5-listtforeach-can-throw-exception-when-modifying-list-item"></a>5: List<>\>. 목록 항목을 수정 하는 경우 ForEach 예외를 throw 할 수 있습니다.  
  
|||  
|-|-|  
|세부 정보|.NET 4.5 부터는 `List<T>.ForEach` 호출 컬렉션의 요소가 수정 된 열거자는 InvalidOperationException 예외를 throw 합니다. 이전에이 예외를 throw 하지 있지만 경합 상태가 발생할 수 있습니다.|  
|제안 해결 방법|이상적으로 것으로 작업이 안전 하 게 하기 때문에 해당 요소를 열거 하는 동안 목록을 수정 하지 않는 코드를 수정 해야 합니다. 그러나 이전 동작으로 되돌리려면 앱.NET 4.0 대상 수 있습니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|대상 변경|  
|영향을 받는 Api|<xref:System.Collections.Generic.List%601.ForEach%28System.Action%7B%600%7D%29?displayProperty=fullName>|  
|분석기|CD0005|  
  
<a name="diagnostic6"></a>   
## <a name="6-systemuri-parsing-adheres-to-rfc-3987"></a>6: RFC 3987 따르는 System.Uri 구문 분석  
  
|||  
|-|-|  
|세부 정보|URI 구문 분석은.NET 4.5의 여러 가지 방법으로 변경 되었습니다. 단, 이러한 변경 내용은.NET 4.5를 대상으로 하는 코드에 영향을 줍니다. 경우 이진 대상이.NET 4.0 이전 버전의 동작 관찰 합니다. .NET 4.5의 URI 구문 분석 변경 내용이 다음과 같습니다.<br /><br /> 정규화 및 RFC 3987의 최신 IRI 규칙에 따라 URI 구문 분석을 수행 합니다.<br /><br /> 유니코드 정규화 형식 C uri 호스트 부분 에서만 수행 됩니다.<br /><br /> 잘못 된 mailto: Uri 예외가 발생 합니다<br /><br /> 경로 세그먼트의 끝에 후행 마침표는 이제 유지<br /><br /> `file://`Uri 이스케이프 되지 않은 `?` 문자<br /><br /> 유니코드 제어 문자 `U+0080` 통해 `U+009F` 지원 되지 않습니다<br /><br /> 쉼표 문자 `,` 또는 `%2c` 자동으로 해제 되지 않습니다|  
|제안 해결 방법|이전.NET 4.0 URI 구문 분석 의미 체계 (경우가 아니더라도) 필요한 경우.NET 4.0을 대상으로 하 여 사용할 수 있습니다. 이 어셈블리에 또는 '프로젝트 속성' 페이지에서 Visual Studio의 프로젝트 시스템 UI 통해 한 TargetFrameworkAttribute를 사용 하 여 수행할 수 있습니다.|  
|범위|주요함|  
|버전|4.5|  
|형식|대상 변경|  
|영향을 받는 Api|<xref:System.Uri.%23ctor%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.Uri%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.String%2CSystem.UriKind%2CSystem.Uri%40%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.Uri%2CSystem.String%2CSystem.Uri%40%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.Uri%2CSystem.Uri%2CSystem.Uri%40%29?displayProperty=fullName>|  
|분석기|CD0006D<br /><br /> CD0006C<br /><br /> CD0006F<br /><br /> CD0006E<br /><br /> CD0006A<br /><br /> CD0006G<br /><br /> CD0006B|  
  
<a name="diagnostic10"></a>   
## <a name="10-systemuri-escaping-now-supports-rfc-3986-httptoolsietforghtmlrfc3986"></a>10: RFC 3986 (http://tools.ietf.org/html/rfc3986)는 이제 지원 System.Uri 이스케이프  
  
|||  
|-|-|  
|세부 정보|지원 하기 위해.NET 4.5에서 변경 된 URI 이스케이프 [RFC 3986](http://tools.ietf.org/html/rfc3986)합니다. 특정 변경 내용이 포함 합니다.<br /><br /> `EscapeDataString`은 RFC 3986을 기반으로 하는 예약된 문자를 이스케이프합니다.<br /><br /> `EscapeUriString`은 예약된 문자를 이스케이프하지 않습니다.<br /><br /> `UnescapeDataString`은 잘못된 이스케이프 시퀀스가 발생하는 경우 예외를 throw하지 않습니다.<br /><br /> 예약되지 않은 이스케이프된 문자는 이스케이프 해제됩니다.|  
|제안 해결 방법|잘못 된 이스케이프 시퀀스의 경우 throw UnescapeDataString에 의존 하지 응용 프로그램을 업데이트 합니다. 이러한 시퀀스를 검색 해야 직접 이제.<br /><br /> 마찬가지로, 되 Escaped 및 이스케이프 되지 않은 URI와 데이터 문자열.NET 4.0 및.NET 4.5에서 다를 수 있습니다 고 직접.NET 버전에 걸쳐 비교 하지 해야 중복. 대신, 이러한 해야 구문 분석 하 고 모든 비교 하기 전에 단일.NET 버전에 표준화 합니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Uri.EscapeDataString%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.EscapeUriString%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.UnescapeDataString%28System.String%29?displayProperty=fullName>|  
|분석기|CD0010A<br /><br /> CD0010B<br /><br /> CD0010C|  
  
<a name="diagnostic11"></a>   
## <a name="11-systemnetpeertopeercollaboration-unavailable-on-windows-8"></a>11: System.Net.PeerToPeer.Collaboration Windows 8에서 사용할 수 없음  
  
|||  
|-|-|  
|세부 정보|System.Net.PeerToPeer.Collaboration 네임 스페이스 이상 Windows 8에 제공 되지 않습니다.|  
|제안 해결 방법|Windows 8을 지원 하거나 위를 업데이트 해야이 네임 스페이스 또는 해당 멤버에 의존 하지 여부를 지정 하는 응용 프로그램|  
|범위|주요함|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Net.PeerToPeer.Collaboration?displayProperty=fullName>|  
|분석기|CD0011|  
  
<a name="diagnostic12"></a>   
## <a name="12-mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a>12: MEF 카탈로그는 IEnumerable을 구현 하 고 따라서 더 이상 사용할 수 없습니다 serializer를 만들려면  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.5부터 MEF 카탈로그 IEnumerable을 구현 하 고 따라서 더 이상 사용할 수 없습니다 serializer (XmlSerializer 개체)를 만듭니다. MEF 카탈로그를 serialize하려고 하면 예외가 throw됩니다.|  
|제안 해결 방법|Serializer를 만들려면 MEF를 더 이상 사용할 수 없습니다.|  
|범위|주요함|  
|버전|4.5|  
|형식|런타임|  
|분석기|CD0012|  
  
<a name="diagnostic13"></a>   
## <a name="13-missing-target-framework-moniker-results-in-40-behavior"></a>13: 대상 프레임 워크 모니커 누락 4.0 동작이 발생  
  
|||  
|-|-|  
|세부 정보|응용 프로그램는 [TargetFrameworkAttribute](https://msdn.microsoft.com/en-us/library/system.runtime.versioning.targetframeworkattribute\(v=vs.110\).aspx) 에서.NET Framework 4.0의 의미 체계 (쿼크)를 사용 하 여 자동으로 실행 하는 어셈블리 수준을 적용 합니다. 높은 품질을 보장 하려면 모든 바이너리로 빌드된 TargetFrameworkAttribute.NET Framework의 버전을 나타내는로 명시적으로 지정 되어야 하 것이 좋습니다. 이때 프로젝트 파일에서 대상 프레임 워크 모니커를 사용 하 여 caues MSBuild는 TargetFrameworkAttribute 자동으로 적용 되도록 합니다.|  
|제안 해결 방법|A [대상 프레임 워크 특성](https://msdn.microsoft.com/en-us/library/system.runtime.versioning.targetframeworkattribute\(v=vs.110\).aspx) 제공 해야, 어셈블리에 직접 또는에 대상 프레임 워크를 지정 하 여 특성을 추가 하는 과정 중 하나는 [프로젝트 파일 또는 Visual Studio를 통해 프로젝트 속성 GUI](http://blogs.msdn.com/b/visualstudio/archive/2010/05/19/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework.aspx)합니다.|  
|범위|주요함|  
|버전|4.5|  
|형식|런타임|  
|분석기|CD0013|  
  
<a name="diagnostic14"></a>   
## <a name="14-no-longer-able-to-set-enableviewstatemac-to-false"></a>14: 더 이상 EnableViewStateMac false로 설정 하려면  
  
|||  
|-|-|  
|세부 정보|ASP.NET 더 이상를 지정할 수 있으며 `<pages enableViewStateMac="false"/>` 또는 `<@Page EnableViewStateMac="false" %>`합니다. 포함된 뷰 상태가 사용된 모든 요청에 뷰 상태 MAC(메시지 인증 코드)가 적용됩니다. 명시적으로 EnableViewStateMac 속성을 false로 설정 하는 유일한 앱에 영향을 받습니다.|  
|제안 해결 방법|EnableViewStateMac true 인 것으로 간주 해야 하 고 모든 결과 MAC 오류 확인 되어야 합니다 (에 설명 된 대로 [이](https://support.microsoft.com/en-us/kb/2915218) MAC 오류 원인을의 세부 사항에 따라 여러 해상도 포함 하는 지침).|  
|범위|주요함|  
|버전|4.5.2|  
|형식|런타임|  
|분석기|CD0014|  
  
<a name="diagnostic18"></a>   
## <a name="18-blockingcollectionttrytakefromany-does-not-throw-anymore"></a>18: BlockingCollection<>\>합니다. TryTakeFromAny 더 이상 throw 하지 않습니다.  
  
|||  
|-|-|  
|세부 정보|입력된 컬렉션 중 하나가 완료, 표시 되는 경우 `BlockingCollection<T>.TryTakeFromAny(BlockingCollection<T>[], T)` 더 이상-1을 반환 하 고 `BlockingCollection<T>.TakeFromAny` 더 이상 예외를 throw 합니다. 이러한 변경을 통해 컬렉션 중 하나가 비어 있거나 완료되었더라도 나머지 컬렉션에는 검색할 수 있는 항목이 아직 있는 경우 컬렉션을 사용할 수 있습니다.|  
|제안 해결 방법|사용 하 여 이제 이러한 코드를 변경 해야-1 또는 TakeFromAny throw 반환 TryTakeFromAny 제어 흐름으로 완료 되 고 차단 수집 하는 경우에 사용 된 경우 `.Any(b => b.IsCompleted)` 조건을 검색할 수 있습니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|[BlockingCollection<>\>합니다. TakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName><br /><br /> [BlockingCollection<>\>합니다. TakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> [BlockingCollection<>\>합니다. TryTakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName><br /><br /> [BlockingCollection<>\>합니다. TryTakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.Int32%29?displayProperty=fullName><br /><br /> [BlockingCollection<>\>합니다. TryTakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.TimeSpan%29?displayProperty=fullName>|  
|분석기|CD0018A<br /><br /> CD0018B|  
  
<a name="diagnostic19"></a>   
## <a name="19-xmlschemaexception-now-sets-line-positions-properly"></a>19: XmlSchemaException 집합 위치를 제대로 줄 이제  
  
|||  
|-|-|  
|세부 정보|LoadOptions.SetLineInfo 값이 Load 메서드에 전달 되는 유효성 검사 오류가 발생 하는 경우 XmlSchemaException.LineNumber 및 XmlSchemaException.LinePosition 속성 이제 줄 정보를 포함 합니다.|  
|제안 해결 방법|XmlSchemaException.LineNumber 및 XmlSchemaException.LinePosition 가정 하는 예외 처리 코드가 됩니다 SetLineInfo XML을 로드 하는 동안 사용 되는 경우 이러한 속성이 제대로 설정 이제는 집합을 업데이트 해야 합니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Xml.Linq.LoadOptions?displayProperty=fullName>|  
|분석기|CD0019|  
  
<a name="diagnostic20"></a>   
## <a name="20-systemactivities-is-now-aptca"></a>20: System.Activities APTCA 되었습니다.  
  
|||  
|-|-|  
|세부 정보|어셈블리는 AllowPartiallyTrustedCallersAttribute 특성으로 표시 됩니다.|  
|제안 해결 방법|파생된 클래스는 SecurityCriticalAttribute로 표시할 수 없습니다. 이전에 파생된 형식을 SecurityCriticalAttribute로 표시 해야 했습니다. 그러나 이 변경은 실제로 영향을 주어서는 안 됩니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|분석기|CD0020|  
  
<a name="diagnostic21"></a>   
## <a name="21-workflow-30-types-are-obsolete"></a>21: 워크플로 3.0 형식을 사용 되지 않습니다.  
  
|||  
|-|-|  
|세부 정보|Workflow Foundation WWF (Windows) 3.0 Api (System.Workflow 네임 스페이스에서 해당) 이제 사용 되지 않습니다.|  
|제안 해결 방법|새 WWF 4.0 Api (system.activities에서)를 대신 사용 해야 합니다. 새 Api를 사용 하는 예제를 찾을 수 있습니다 [여기](https://msdn.microsoft.com/en-us/library/jj205427.aspx) 추가 지침을 사용할 수 및 [여기](http://blogs.msdn.com/b/workflowteam/archive/2012/02/08/deprecatingwf3.aspx)합니다. 또는 WWF 3.0 Api는 계속 지원 하므로 사용할 수 있습니다. 있으며 표시 되지 않도록 하거나 한 이전 컴파일러를 사용 하 여 빌드 시간 경고를 피할 수 있습니다.|  
|범위|주요함|  
|버전|4.5|  
|형식|대상 변경|  
|분석기|CD0021|  
  
<a name="diagnostic22"></a>   
## <a name="22-some-workflow-drag-and-drop-apis-are-obsolete"></a>22: 일부 워크플로 끌어서 놓기 Api 사용 되지 않습니다.  
  
|||  
|-|-|  
|세부 정보|이 워크플로 끌어서 놓기 API는 사용 되지 않으며 4.5에 대 한 응용 프로그램은 다시 빌드하는 경우 컴파일러 경고가 발생 합니다.|  
|제안 해결 방법|새 [DragDropHelper](https://msdn.microsoft.com/en-us/library/system.activities.presentation.dragdrophelper\(v=vs.110\).aspx) 여러 개체에 대 한 작업을 지 원하는 Api를 대신 사용 해야 합니다. 또는 빌드 경고를 억제할 수 있습니다 하거나 한 이전 컴파일러를 사용 하 여 방지할 수 있습니다. Api는 계속 지원 됩니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|대상 변경|  
|영향을 받는 Api|<xref:System.Activities.Presentation.DragDropHelper.DoDragMove%28System.Activities.Presentation.WorkflowViewElement%2CSystem.Windows.Point%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView%28System.Windows.DragEventArgs%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem%28System.Windows.DragEventArgs%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject%28System.Windows.DependencyObject%2CSystem.Windows.DragEventArgs%2CSystem.Activities.Presentation.EditingContext%29?displayProperty=fullName>|  
|분석기|CD0022|  
  
<a name="diagnostic23"></a>   
## <a name="23-new-ambiguous-dispatcherinvoke-overloads-could-result-in-different-behavior"></a>23: 다른 동작 (모호한) 새 Dispatcher.Invoke 오버 로드 될 수 있습니다  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.5를 Dispatcher.Invoke System.Action 형식의 매개 변수를 포함 하는 새 오버 로드를 추가 합니다. 기존 코드를 다시 컴파일할 때 컴파일러는 System.Action 매개 변수를 사용 하 여 Dispatcher.Invoke 메서드 호출으로 대리자 매개 변수가 있는 Dispatcher.Invoke 메서드 호출을 해결할 수 있습니다. 대리자 매개 변수가 Dispatcher.Invoke 오버 로드에 대 한 호출 System.Action 매개 변수를 사용 하는 Dispatcher.Invoke 오버 로드에 대 한 호출으로 해결 되 면 다음과 같은 동작 차이가 발생할 수 있습니다.<br /><br /> 예외가 발생 하는 경우에 Dispatcher.UnhandledExceptionFilter 및 Dispatcher.UnhandledException 이벤트가 발생 하지 않습니다. 대신, 예외 UnobservedTaskException 이벤트에 의해 처리 됩니다.<br /><br /> DispatcherOperation.Result와 같은 일부 멤버에 대 한 호출에는 작업이 완료 될 때까지 차단 합니다.|  
|제안 해결 방법|방지 하려면 모호성 (및 예외를 처리 하거나 차단 하는 동작의 잠재적인 문제)을 호출 Dispatcher.Invoke 코드에 전달할 수 있는 빈 개체 두 번째 매개 변수로.NET 4.0 메서드 오버 로드를 확인 하도록 하려면 Invoke 호출.|  
|범위|사소함|  
|버전|4.5|  
|형식|대상 변경|  
|영향을 받는 Api|[Dispatcher.Invoke (위임, o b j\<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> [Dispatcher.Invoke (대리자, TimeSpan 개체\<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.TimeSpan%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> [Dispatcher.Invoke (대리자, DispatcherPriority, TimeSpan 개체\<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.TimeSpan%2CSystem.Windows.Threading.DispatcherPriority%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> [Dispatcher.Invoke (대리자, DispatcherPriority, 개체\<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.Windows.Threading.DispatcherPriority%2CSystem.Object%5B%5D%29?displayProperty=fullName>|  
|분석기|CD0023|  
  
<a name="diagnostic24"></a>   
## <a name="24-encoderparameter-ctor-is-obsolete"></a>24: EncoderParameter ctor 사용 되지 않습니다.  
  
|||  
|-|-|  
|세부 정보|`EncoderParameter.EncoderParameter(Encoder, Int32, Int32, Int32)` 생성자는 이제 사용 되지 않습니다 하 고 사용 하는 경우 빌드 경고를 소개 합니다.|  
|제안 해결 방법|하지만 `EncoderParameter.EncoderParameter(Encoder, Int32, Int32, Int32)` 생성자는 계속 작동,.NET 4.5 도구를 사용 하 여 코드를 다시 컴파일할 때 사용 되지 않는 빌드 경고를 방지 하려면 다음 생성자를 대신 사용 해야 합니다. [EncoderParameter.EncoderParameter (인코더, Int32, EncoderParameterValueType, IntPtr)](https://msdn.microsoft.com/en-us/library/hh875096\(v=vs.110\).aspx)합니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|대상 변경|  
|영향을 받는 Api|<xref:System.Drawing.Imaging.EncoderParameter.%23ctor%28System.Drawing.Imaging.Encoder%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|분석기|CD0024|  
  
<a name="diagnostic26"></a>   
## <a name="26-change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a>26: 제한 시간 인수가 있는 Task.WaitAll 메서드 동작이 변경  
  
|||  
|-|-|  
|세부 정보|.NET 4.5에서 Task.WaitAll 동작 보다 일관성 있게 했습니다.<br /><br /> .NET Framework 4에서 이러한 메서드 동작 했었습니다. 하나 이상의 작업이 완료 되거나 취소 메서드를 호출 하기 전에 제한 시간이 만료 될 때 메서드 AggregateException 예외가 발생 했습니다. 작업이 완료 되거나 취소 메서드 호출 전에 하나 이상의 작업 메서드 호출 후 이러한 상태를 입력 한 경우 제한 시간이 만료 될 때이 메서드는 false를 반환.<br />.NET Framework 4.5에서 이러한 메서드 오버 로드는 이제 모든 작업은 시간 제한 간격이 만료 되었는데 (에 관계 없이 여부를 메서드 호출 전후)는 입력된 작업이 취소 되 고 다른 작업이 실행 중인 경우에 AggregateException 예외가 throw 하는 경우 실행 중인 경우 false를 반환 합니다.|  
|제안 해결 방법|코드는 IsCanceled 속성을 통해 동일한 검색을 수행 해야 할 대신 호출 중인 WaitAll 호출 하기 전에 취소 된 작업을 검색 하는 수단으로는 AggregateException를 발견 하 고 된 경우 (예:. 모든 (t t.IsCanceled =>)).NET 4.6만 발생이 경우 모든 대기 중인된 작업이 완료 된 시간 제한 전에 때문입니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|[Task.WaitAll (작업\<xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.Int32%29?displayProperty=fullName><br /><br /> [Task.WaitAll (작업\<xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.Int32%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> [Task.WaitAll (작업\<xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.TimeSpan%29?displayProperty=fullName>|  
|분석기|CD0026|  
  
<a name="diagnostic27"></a>   
## <a name="27-change-in-behavior-in-data-definition-language-ddl-apis"></a>27: 데이터 정의 언어 (DDL) Api의 동작 변경  
  
|||  
|-|-|  
|세부 정보|AttachDBFilename을 지정 하는 DDL Api의 동작은 다음과 같이 변경 되었습니다.<br /><br /> 연결 문자열에 초기 카탈로그 값을 지정할 필요가 있습니다. 이전에 AttatchDBFilename 및 초기 카탈로그를 모두 필요 했습니다.<br /><br /> AttatchDBFilename 및 초기 카탈로그를 모두 지정 하는 경우 제공 된 MDF 파일이 있는 ObjectContext.DatabaseExists 메서드는 true를 반환 합니다. 이전에 false 반환 합니다.<br /><br /> AttatchDBFilename 및 초기 카탈로그를 모두 지정 하는 경우 제공 된 MDF 파일이 있는 파일 삭제 ObjectContext.DeleteDatabase 메서드를 호출 합니다.<br /><br /> ObjectContext.DeleteDatabase를를 호출 하면 연결 문자열은 존재 하지 않는 한 MDF 및 존재 하지 않는 초기 카탈로그를 사용 하 여 AttachDBFilename 값을 지정 하는 경우 메서드는 InvalidOperationException 예외를 throw 합니다. 이전에 SqlException 예외를 했습니다.|  
|제안 해결 방법|이러한 변경으로 인해 DDL API를 사용하는 도구와 응용 프로그램을 보다 쉽게 빌드할 수 있습니다. 이러한 변경 사항은 다음 시나리오에서 응용 프로그램 호환성에 영향을 줄 수 있습니다.<br /><br /> 사용자는 ObjectContext.DatabaseExists 경우 true를 반환 하는 대신 직접 호출 ObjectContext.DeleteDatabase DROP DATABASE 명령을 실행 하는 코드를 씁니다. 이는 데이터베이스가 연결되지 않았지만 MDF 파일이 있는 경우 기존 코드를 중단시킵니다.<br /><br /> 사용자는 초기 카탈로그 및 MDF 파일이 없을 때 InvalidOperationException 예외 보다는 SqlException 예외를 throw 하려면 ObjectContext.DeleteDatabase 메서드 기대 되는 코드를 씁니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|분석기|CD0027|  
  
<a name="diagnostic28"></a>   
## <a name="28-machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a>28: MachineKey.Encode 및 MachineKey.Decode 메서드는 이제 사용 되지 않습니다  
  
|||  
|-|-|  
|세부 정보|이러한 메서드는 이제 사용되지 않습니다. 이러한 메서드를 호출하는 코드를 컴파일하면 컴파일러 경고가 생성됩니다.|  
|제안 해결 방법|권장 되는 대체는 [MachineKey.Protect](https://msdn.microsoft.com/en-us/library/system.web.security.machinekey.protect\(v=vs.110\).aspx) 및 [MachineKey.Unprotect](https://msdn.microsoft.com/en-us/library/system.web.security.machinekey.unprotect\(v=vs.110\).aspx)합니다. 또는 빌드 경고를 억제할 수 있습니다 하거나 한 이전 컴파일러를 사용 하 여 방지할 수 있습니다. Api는 계속 지원 됩니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|대상 변경|  
|영향을 받는 Api|<xref:System.Web.Security.MachineKey.Decode%28System.String%2CSystem.Web.Security.MachineKeyProtection%29?displayProperty=fullName><br /><br /> [MachineKey.Encode (바이트\<xref:System.Web.Security.MachineKey.Encode%28System.Byte%5B%5D%2CSystem.Web.Security.MachineKeyProtection%29?displayProperty=fullName>|  
|분석기|CD0028|  
  
<a name="diagnostic29"></a>   
## <a name="29-the-replace-method-in-odata-urls-is-disabled-by-default"></a>29: OData Url의 Replace 메서드는 기본적으로 비활성화 되어 있습니다.  
  
|||  
|-|-|  
|세부 정보|OData Url의 Replace 메서드는.NET Framework 4.5 부터는 기본적으로 비활성화 됩니다. OData Replace는 이제 기본적으로 비활성화 되 면 (일반적이 지 않은)는 replace 함수를 포함 하 여 모든 사용자 요청 실패 합니다.|  
|제안 해결 방법|Replace 메서드 필요한 경우 (되지 않는 일반적인)를 통해 다시 설정할 수 있습니다는 [구성 설정을](https://msdn.microsoft.com/en-us/library/system.data.services.configuration.dataservicesfeaturessection.replacefunction.aspx)합니다. 그러나 활성화 된 replace 메서드 보안 취약점을 열 수 및 신중 하 게 검토 한 후에 사용 해야 합니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Data.Services.DataService%601?displayProperty=fullName>|  
|분석기|CD0029|  
  
<a name="diagnostic30"></a>   
## <a name="30-systemservicemodelwebwebservicehost-object-no-longer-adds-a-default-endpoint"></a>30: System.ServiceModel.Web.WebServiceHost 개체는 더 이상 기본 끝점을 추가  
  
|||  
|-|-|  
|세부 정보|System.ServiceModel.Web.WebServiceHost 개체는 명시적 끝점이 응용 프로그램 코드에 의해 추가 된 경우에 더 이상 기본 끝점을 추가 합니다.|  
|제안 해결 방법|사용자가 기본 끝점에 연결할 수 있게 되기를 기대 하는 경우 다른 명시적 끝점 WebServiceHost에 추가 된 기본 끝점도 추가 되어야 명시적으로 (AddDefaultEndpoints 사용).|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.ServiceModel.Description.ServiceEndpoint%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%2CSystem.Uri%29?displayProperty=fullName>|  
|분석기|CD0030A<br /><br /> CD0030B|  
  
<a name="diagnostic31"></a>   
## <a name="31-eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a>31: EventSource.WriteEvent impls WriteEvent가 (ID) 더하기 수신한 동일한 매개 변수를 전달 해야 합니다  
  
|||  
|-|-|  
|세부 정보|이제 런타임에서 다음을 지정 하는 계약을 적용 합니다: ETW 이벤트 메서드를 정의 하는 EventSource에서 파생 된 클래스는 이벤트 id 다음에 ETW 이벤트 메서드가 전달 된 동일한 인수 EventSource.WriteEvent 메서드는 기본 클래스를 호출 해야 합니다.|  
|제안 해결 방법|EventListener이이 계약을 위반 하는 이벤트 소스에 대 한 프로세스의 EventSource 데이터를 읽는 경우 IndexOutOfRangeException 예외가 throw 됩니다.|  
|범위|사소함|  
|버전|4.5.1|  
|형식|런타임|  
|분석기|CD0031|  
  
<a name="diagnostic32"></a>   
## <a name="32-minfreememorypercentagetoactiveservice-is-now-respected"></a>32: MinFreeMemoryPercentageToActiveService가 지금 적용  
  
|||  
|-|-|  
|세부 정보|이 설정은 WCF 서비스를 활성화할 수 있습니다 서버에서 사용할 수 있어야 하는 최소 메모리를 설정 합니다. OutOfMemoryException 예외를 방지 하기 위해 설계 되었습니다. .NET Framework 4.5에서이 설정은 영향을 주지 않았습니다. .NET Framework 4.5.1의에서 해당 설정이 적용 됩니다.|  
|제안 해결 방법|웹 서버의 사용 가능한 메모리가 구성 설정에서 정의된 백분율보다 적은 경우 예외가 발생합니다. 성공적으로 시작되었지만 제한된 메모리 환경에서 실행되는 일부 WCF 서비스의 경우 실패할 수 있습니다.|  
|범위|사소함|  
|버전|4.5.1|  
|형식|런타임|  
|분석기|CD0032|  
  
<a name="diagnostic33"></a>   
## <a name="33-xmltextreader-dtd-entity-expansion-is-limited-to-10000000-characters"></a>33: XmlTextReader DTD 엔터티 확장은 10000000 자로 제한 됩니다.  
  
|||  
|-|-|  
|세부 정보|DTD 엔터티 확장은 이제 10000000 자로 제한 됨. DTD 엔터티 확장 없이 또는 제한된 DTD 엔터티 확장으로 XML 파일을 로드해도 영향을 받지 않습니다. 이제 파일에 10,000,000자를 초과하는 문자로 확장되는 DTD 엔터티가 있으면 로드하지 못하고 예외를 throw합니다.|  
|제안 해결 방법|DTD 엔터티 확장의 제한 값이 너무 낮게 10000000를 값으로 재정의 될 수는 [XmlReaderSettings.MaxCharactersFromEntities](https://msdn.microsoft.com/en-us/library/system.xml.xmlreadersettings.maxcharactersfromentities%28v=vs.110%29.aspx) 속성입니다. 적절 한 MaxCharactersFromEntity 값으로는 XmlReaderSettings에 전달할 수 [XmlReader.Create](https://msdn.microsoft.com/en-us/library/System.Xml.XmlReader.Create\(v=vs.110\).aspx)|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Xml.XmlTextReader.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%2CSystem.Xml.XmlNodeType%2CSystem.Xml.XmlParserContext%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.TextReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.TextReader%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.Stream%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.TextReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.TextReader%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.Xml.XmlNodeType%2CSystem.Xml.XmlParserContext%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader?displayProperty=fullName>|  
|분석기|CD0033|  
  
<a name="diagnostic35"></a>   
## <a name="35-xslt-style-sheet-exception-message-changed"></a>35: XSLT 스타일 시트 예외 메시지 변경  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.5에서 XSLT 파일이 너무 복잡할 경우 오류 메시지의 텍스트는 "스타일 시트가 너무 복잡 합니다." 이전 버전에서 오류 메시지는 "XSLT 컴파일 오류입니다."였습니다. 오류 메시지 텍스트에 종속되어 있는 응용 프로그램 코드는 더 이상 작동하지 않습니다. 그러나 예외 형식은 동일 하 게 유지, 되므로이 변경은 실제 영향을 미쳐서는 안 됩니다.|  
|제안 해결 방법|새 메시지를 예상 하 여이 오류 조건에서 excepton 메시지에 따라 응용 프로그램 코드 (더욱)는 예외 형식에만 의존 하는 코드를 업데이트 하거나 ([XsltException](https://msdn.microsoft.com/en-us/library/system.xml.xsl.xsltexception\(v=vs.110\).aspx)), 변경 되지 않았습니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|[XslCompiledTransform.Load (MethodInfo, 바이트\[\], 형식\<xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Reflection.MethodInfo%2CSystem.Byte%5B%5D%2CSystem.Type%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.String%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XPath.IXPathNavigable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XPath.IXPathNavigable%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XmlReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XmlReader%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName>|  
|분석기|CD0035|  
  
<a name="diagnostic36"></a>   
## <a name="36-wf-serializes-expressionsliteralt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>36: WF serialize Expressions.Literal<> \</> \> 날짜/시간은 다르게 이제 (사용자 지정 XAML 파서가 나누기)  
  
|||  
|-|-|  
|세부 정보|연결 된 [ValueSerializer](https://msdn.microsoft.com/en-us/library/system.windows.markup.valueserializer\(v=vs.110\).aspx) 개체는 변환 DateTime 또는 DateTimeOffset 개체를 초 및 밀리초 구성 요소는&0;이 아닌 값 (날짜/시간에 대 한 값) 인 DateTime.Kind 속성은 문자열 대신에 속성 요소 구문에 알 수 없습니다. DateTime과 DateTimeOffset 값을 라운드트립 아니어도이 변경할 수 있습니다. 입력 XAML이 특성 구문에 있다고 가정하는 사용자 지정 XAML 파서가 올바르게 작동하지 않습니다.|  
|제안 해결 방법|DateTime과 DateTimeOffset 값을 라운드트립 아니어도이 변경할 수 있습니다. 입력 XAML이 특성 구문에 있다고 가정하는 사용자 지정 XAML 파서가 올바르게 작동하지 않습니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|분석기|CD0036|  
  
<a name="diagnostic37"></a>   
## <a name="37-new-enum-values-in-wpfs-pagerangeselection"></a>37: WPF의 PageRangeSelection에 새 열거형 값  
  
|||  
|-|-|  
|세부 정보|에 추가 된 두 명의 새 멤버 (CurrentPage 및 SelectedPage)는 [PageRangeSelection](https://msdn.microsoft.com/en-us/library/system.windows.controls.pagerangeselection\(v=vs.110\).aspx) 열거형입니다.|  
|제안 해결 방법|대부분의 경우에서 이러한 변경 내용은 사용자 코드에 영향을 하지 않습니다. 특정 수의 Enum.GetNames 또는 Enum.GetValues에 존재 하는 요소에 종속 되어 있는 코드 형식을 수정 해야, 그러나 PageRangeSelection를 호출 합니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>|  
|분석기|CD0037|  
  
<a name="diagnostic38"></a>   
## <a name="38-wpf-dispatchersynchronizationcontextcreatecopy-now-returns-a-new-copy-instead-of-the-current-instance"></a>38: WPF DispatcherSynchronizationContext.CreateCopy 대신 현재 인스턴스의 새 복사본을 반환  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4 DispatcherSynchronizationContext.CreateCopy() 주로 성능 최적화 기능으로 현재 인스턴스에 대 한 참조를 반환 합니다. .NET Framework 4.5를 올바른 동기화 컨텍스트에서 실행 되는 스레드를 나타내는 동일한 참조가 완료 하기 위해 처음으로 수 있는 새 인스턴스를 반환 합니다.  이러한 참조의 id를 확인 하는 코드가 영향을 하지만, 변경으로 인해.NET Framework 4.5로 마이그레이션의 일부로 DispatcherSynchronizationContext.CreateCopy를 호출 하는 코드를 테스트 하기 어렵거나 최신 이며|  
|제안 해결 방법|주의 DispatcherSynchronizationContext.CreateCopy()은 이제 새로운 SynchronizationContext 개체를 반환 합니다.  이전에 이러한 방식으로 생성 된 참조의 동등성을 사용 하는 코드를 적절 한 컨텍스트에.NET 4.5에 대해 또는 최신 버전을 빌드할 때 지 실제로 확인 하지.  낮지만 하면 문제가 발생할 수 영향을 받는 코드 경로 실행 해야 어떤 문제가 발생 하는 경우를 파악 하기에 충분 합니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=fullName>|  
|분석기|CD0038|  
  
<a name="diagnostic39"></a>   
## <a name="39-systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a>39: 개체를 삭제 한 후 더 이상 System.Threading.Tasks.Task ObjectDisposedException throw  
  
|||  
|-|-|  
|세부 정보|Task.IAsyncResult.AsyncWaitHandle를 제외 하 고 System.Threading.Tasks.Task 메서드 더 이상 ObjectDisposedException 예외가 throw 된 개체를 삭제 한 후.<br />이 변경은 캐시된 작업의 사용을 지원합니다. 예를 들어, 메서드는 새로운 작업을 할당하는 대신에 이미 완료된 작업을 나타내기 위해 캐시된 작업을 반환할 수 있습니다. 작업의 모든 소비자는 다시 사용할 수 없게 렌더링된 작업을 삭제할 수 있었기 때문에 이전 .NET Framework 버전에서는 이것이 불가능했습니다.|  
|제안 해결 방법|작업 메서드는 개체가 삭제 될 때과 ObjectDisposedExceptions의 경우에서에 throw 더 이상 할 수 없습니다. 업데이트를 명시적으로 작업의 상태를 확인 해야 앱이이 예외는 작업을 삭제 했습니다 알아야 느끼고, 하는 경우를 사용 하 여 [Task.Status](https://msdn.microsoft.com/en-us/library/system.threading.tasks.task.status\(v=vs.110\).aspx)합니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|분석기|CD0039|  
  
<a name="diagnostic40"></a>   
## <a name="40-different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a>40: ObjectContext.CreateDatabase 및 DbProviderServices.CreateDatabase 메서드를 처리 하는 다른 예외  
  
|||  
|-|-|  
|세부 정보|데이터베이스 만들기에 실패 하면.NET 4.5 부터는 `CreateDatabase` 메서드는 빈 데이터베이스를 삭제 하려고 합니다. 해당 작업에 성공 하면 원래 `SQLException` 전파 됩니다 (대신는 `InvalidOperationException` 항상.NET 4.0에서 throw 된)|  
|제안 해결 방법|ObjectContext.CreateDatabase 또는 DbProviderServices.CreateDatabase를 실행 하는 동안 InvalidOperationException를 포착할 때 SQLExceptions 이제도 발견 됩니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Data.Common.DbProviderServices.CreateDatabase%28System.Data.Common.DbConnection%2CSystem.Nullable%7BSystem.Int32%7D%2CSystem.Data.Metadata.Edm.StoreItemCollection%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName>|  
|분석기|CD0040|  
  
<a name="diagnostic41"></a>   
## <a name="41-objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a>41: ObjectContext.Translate와 ObjectContext.ExecuteStoreQuery 열거형 형식 지원  
  
|||  
|-|-|  
|세부 정보|.NET 4.0, 제네릭 매개 변수에서에서 `T` 의 `ObjectContext.Translate` 및 `ObjectContext.ExecuteStoreQuery` 메서드 열거형 수 없습니다. 이 시나리오는 지원 됩니다.|  
|제안 해결 방법|번역 또는 ExecuteStoreQuery.NET 4.0에는 열거형에서 호출 된, '0'이 반환 되었습니다. 동작을 하는 것이 호출 하 여 상수 0 (또는 enum 해당 하는 것)로 바꿔야 합니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|[ObjectContext.ExecuteStoreQuery<>\>(문자열, 개체\<xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601%28System.String%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> [ObjectContext.ExecuteStoreQuery<>\>(문자열, 문자열, MergeOption, 개체\<xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601%28System.String%2CSystem.String%2CSystem.Data.Objects.MergeOption%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.Translate%60%601%28System.Data.Common.DbDataReader%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.Translate%60%601%28System.Data.Common.DbDataReader%2CSystem.String%2CSystem.Data.Objects.MergeOption%29?displayProperty=fullName>|  
|분석기|CD0041|  
  
<a name="diagnostic42"></a>   
## <a name="42-enumerableemptytresult-always-returns-cached-instance"></a>42: Enumerable.Empty<> \</> \> 캐시 된 인스턴스가 항상 반환  
  
|||  
|-|-|  
|세부 정보|.NET 4.5 부터는 `Enumerable.Empty` 항상 캐시 된 내부 인스턴스를 반환 `IEnumerable<T>`합니다.<br /><br /> 이전에 `Enumerable.Empty` 빈 캐시는 `IEnumerable<T>` API가 호출 된 시간에는 몇 가지 조건에 의미 `Enumerable.Empty` 호출한 신속 하 고 동시에 다른 형식의 인스턴스를 API에 대 한 다른 호출에 대 한 반환 될 수 없습니다.|  
|제안 해결 방법|이전 동작 명확 하지 않아 코드에 의존 하는 많지 않습니다. 그러나 빈 열거 가능 형식 비교 되 고 때로는 같지 않은 것으로 예상 하는 드물지만, 명시적 빈 배열을 만들어야 (`new T[0]`) 사용 하는 대신 `Enumerable.Empty`합니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Linq.Enumerable.Empty%60%601?displayProperty=fullName>|  
|분석기|CD0042|  
  
<a name="diagnostic43"></a>   
## <a name="43-httprequestcontentencoding-property-prohibits-utf7"></a>43: HttpRequest.ContentEncoding 속성 UTF7를 금지 합니다.  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.5 부터는 utf-7 인코딩은 HttpRequests의 본문에서 금지 됩니다. 경우에 따라 UTF-7 수신 데이터에 종속되는 응용 프로그램 데이터가 제대로 디코딩되지 않습니다.|  
|제안 해결 방법|이상적으로 HttpRequests에서 인코딩을 u t F-7을 사용 하지 않도록 응용 프로그램을 업데이트 되어야 합니다. 또는 사용 하 여 레거시 동작을 복원할 수 있습니다는 `aspnet:AllowUtf7RequestContentEncoding` 의 특성은 [appSettings](https://msdn.microsoft.com/en-us/library/hh975440\(v=vs.110\).aspx) 요소입니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Web.HttpRequest.ContentEncoding?displayProperty=fullName>|  
|분석기|CD0043|  
  
<a name="diagnostic44"></a>   
## <a name="44-httputilityjavascriptstringencode-escapes-ampersand"></a>44: HttpUtility.JavaScriptStringEncode 앰퍼샌드를 이스케이프 합니다.  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.5 부터는 JavaScriptStringEncode 앰퍼샌드 (&) 문자를 이스케이프 합니다.|  
|제안 해결 방법|앱이 메서드의 이전 동작에 의존 하는 경우에 하는 aspnet:JavaScriptDoNotEncodeAmpersand 설정을 추가할 수 있습니다는 [ASP.NET appSettings 요소](https://msdn.microsoft.com/en-us/library/hh975440\(v=vs.110\).aspx) 프로그램 구성 파일에 있습니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Web.HttpUtility.JavaScriptStringEncode%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Web.HttpUtility.JavaScriptStringEncode%28System.String%2CSystem.Boolean%29?displayProperty=fullName>|  
|분석기|CD0044A<br /><br /> CD0044B|  
  
<a name="diagnostic46"></a>   
## <a name="46-eventlistener-truncates-strings-with-embedded-nulls"></a>46: EventListener 자릅니다 포함 된 null이 있는 문자열  
  
|||  
|-|-|  
|세부 정보|EventListener 포함 된 null 사용 하 여 문자열을 자릅니다. Null 문자는 EventSource 클래스에서 지원 되지 않습니다. 변경은 프로세스의 EventSource 데이터를 읽는 EventListener를 사용 하는 구분 기호로 null 문자를 사용 하는 앱을만 영향을 줍니다.|  
|제안 해결 방법|가능 하면 포함 된 null 문자를 사용 하지 않도록 EventSource 데이터를 업데이트 되어야 합니다.|  
|범위|Microsoft Edge|  
|버전|4.5.1|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Diagnostics.Tracing.EventListener.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%2CSystem.Diagnostics.Tracing.EventKeywords%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%2CSystem.Diagnostics.Tracing.EventKeywords%2CSystem.Collections.Generic.IDictionary%7BSystem.String%2CSystem.String%7D%29?displayProperty=fullName> \</String, String>|  
|분석기|CD0046|  
  
<a name="diagnostic48"></a>   
## <a name="48-obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>48: ObsoleteAttribute WinMD 시나리오에서 ObsoleteAttribute와 DeprecatedAttribute로 내보내기  
  
|||  
|-|-|  
|세부 정보|Windows 메타 데이터 라이브러리 (.winmd 파일)를 만들 때 ObsoleteAttribute 특성 ObsoleteAttribute와 Windows.Foundation.DeprecatedAttribute로 내보내집니다.|  
|제안 해결 방법|ObsoleteAttribute 특성을 사용 하는 기존 소스 코드를 다시 컴파일하면 C +의 해당 코드가 사용 하는 경우 경고를 생성할 수 있습니다 + /CX 또는 JavaScript입니다.<br /><br /> ObsoleteAttribute 및 Windows.Foundation.DeprecatedAttribute 모두 관리 되는 어셈블리의 코드를 적용 하지 않는 것이 좋습니다. 경고가 발생할 수 있습니다.|  
|범위|Microsoft Edge|  
|버전|4.5.1|  
|형식|대상 변경|  
|분석기|CD0048A<br /><br /> CD0048B|  
  
<a name="diagnostic49"></a>   
## <a name="49-resolveassemblyreference-task-now-warns-on-dependencies-with-the-wrong-architecture"></a>49: 잘못 된 아키텍처와 종속성에 이제에 게 경고 ResolveAssemblyReference 작업  
  
|||  
|-|-|  
|세부 정보|이 작업은 참조 또는 해당 종속성이 앱 아키텍처와 일치하지 않음을 나타내는 경고 MSB3270을 내보냅니다. 예를 들어 이렇게 anycpu 옵션을 사용 하 여 컴파일한 응용 프로그램에 x86 포함 되어 있는 경우 참조 합니다. 이로 인해 앱의 런타임 오류가 발생할 수 있습니다(앱이 x64 프로세스로 배포된 경우).|  
|제안 해결 방법|영향에는 다음 두 가지 영역이 있습니다.<br /><br /> 다시 컴파일하면 앱이 이전 MSBuild 버전에서 컴파일되었을 때는 나타나지 않았던 경고가 생성됩니다. 하지만 런타임 오류가 발생한 소스를 경고에서 확인할 수 있으므로 이 문제를 조사하여 해결할 수 있습니다.<br /><br /> 경고가 오류로 처리되면 앱을 컴파일할 수 없습니다.|  
|범위|사소함|  
|버전|4.5.1|  
|형식|대상 변경|  
|분석기|CD0049|  
  
<a name="diagnostic51"></a>   
## <a name="51-wpf-textbox-defaults-to-undo-limit-of-100"></a>51: WPF TextBox 기본값 100 개로 제한 실행 취소 하려면  
  
|||  
|-|-|  
|세부 정보|.NET 4.5에서는 기본 실행 취소 WPF 텍스트 상자에 대 한 제한은 100 (반대 되 고.NET 4.0에서 무제한)|  
|제안 해결 방법|TextBox의 UndoLimit 속성으로도 실행 취소도 100 너무 낮으면 명시적으로 설정할 수 있습니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Windows.Controls.TextBox?displayProperty=fullName>|  
|분석기|CD0051|  
  
<a name="diagnostic55"></a>   
## <a name="55-exceptions-during-unobserved-processing-in-systemthreadingtaskstask-no-longer-propagate-on-finalizer-thread"></a>55: System.Threading.Tasks.Task에서 관찰 되지 않은 처리 하는 동안 예외는 더 이상 종료자 스레드에서 전파  
  
|||  
|-|-|  
|세부 정보|System.Threading.Tasks.Task 클래스는 비동기 작업을 나타내므로 비동기 처리 하는 동안 발생 하는 심각 하지 않은 모든 예외를 catch 합니다. .NET Framework 4.5에서 예외가 관찰 되지 하 고 코드가 작업에서 대기 하지, 예외는 더 이상 종료자 스레드에서 전파 하 고 가비지 수집 중에 프로세스를 중단 합니다. 이러한 변경으로 인해 관찰 되지 않은 비동기 처리를 수행 하려면 작업 클래스를 사용 하는 응용 프로그램의 안정성을 향상 합니다.|  
|제안 해결 방법|에 대 한 적절 한 처리기를 제공 하 여 이전 동작을 복원할 수는 응용 프로그램 종료자 스레드를 전파 하는 관찰 되지 않은 비동기 예외에 따라 달라 지는 [TaskScheduler.UnobservedTaskException](https://msdn.microsoft.com/en-us/library/system.threading.tasks.taskscheduler.unobservedtaskexception\(v=vs.110\).aspx) 이벤트를 설정 하 여는 [런타임 구성 요소](https://msdn.microsoft.com/en-us/library/jj160346%28v=vs.110%29.aspx)합니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Threading.Tasks.Task.Run%28System.Action%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Action%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%60%600%7D%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%60%600%7D%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7B%60%600%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7B%60%600%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Start?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Start%28System.Threading.Tasks.TaskScheduler%29?displayProperty=fullName>|  
|분석기|CD0055|  
  
<a name="diagnostic58"></a>   
## <a name="58-iasyncresultcompletedsynchronously-property-must-be-correct-for-the-resulting-task-to-complete"></a>58: IAsyncResult.CompletedSynchronously 속성 결과 작업을 완료 하려면 정확 해야 합니다.  
  
|||  
|-|-|  
|세부 정보|TaskFactory.FromAsync를 호출할 때 IAsyncResult.CompletedSynchronously 속성의 구현 결과 작업을 완료 하려면 수정 해야 합니다. 즉, 속성, 하 고 구현 동기적으로 완료 된 경우에 true를 반환 해야 합니다. 이전에는 이 속성이 선택되어 있지 않았습니다.|  
|제안 해결 방법|IAsyncResult 구현을 올바르게 작업이 동기적으로 완료 된 경우에 CompletedSynchronusly 속성에 대해 true를 반환에 나누기 없음 관찰 합니다. 사용자가 올바르게 평가 하는지 여부를 동기적으로 완료 되도록 (있는 경우)를 소유 하는 IAsyncResult 구현을 검토 해야 합니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|대상 변경|  
|영향을 받는 Api|<xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Object%29?displayProperty=fullName> \</AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Threading.Tasks.TaskCreationOptions%2CSystem.Threading.Tasks.TaskScheduler%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Object%29?displayProperty=fullName> \</IAsyncResult, TResult> \</AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult> \</AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2CSystem.Object%29?displayProperty=fullName> </TArg1, AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</TArg1, AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%29?displayProperty=fullName> \</IAsyncResult, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Threading.Tasks.TaskCreationOptions%2CSystem.Threading.Tasks.TaskScheduler%29?displayProperty=fullName> \</IAsyncResult, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%601%7D%2C%60%600%2CSystem.Object%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, AsyncCallback, Object, IAsyncResult> \</TArg1, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%601%7D%2C%60%600%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, AsyncCallback, Object, IAsyncResult> \</TArg1, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2CSystem.Object%29?displayProperty=fullName> </TArg1, TArg2, AsyncCallback, Object, IAsyncResult> </TArg1, TArg2><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</TArg1, TArg2, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%602%7D%2C%60%600%2C%60%601%2CSystem.Object%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, TArg2, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%602%7D%2C%60%600%2C%60%601%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, TArg2, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%29?displayProperty=fullName> </TArg1, TArg2, TArg3, AsyncCallback, Object, IAsyncResult> </TArg1, TArg2, TArg3><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</TArg1, TArg2, TArg3, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TArg3><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%603%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, TArg2, TArg3, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TArg3, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%603%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, TArg2, TArg3, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TArg3, TResult>|  
|분석기|CD0058|  
  
<a name="diagnostic59"></a>   
## <a name="59-log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a>59: ObjectContext.CreateDatabase 메서드에서 만든 로그 파일 이름은 SQL Server 사양에 맞게 변경 되었습니다  
  
|||  
|-|-|  
|세부 정보|경우 CreateDatabase 메서드를 호출 하거나 직접를 사용 하 여 Code First는 SqlClient 공급자와 연결 문자열의 AttachDBFilename 값으로 로그 파일을 만듭니다 명명 된 filename_log.ldf filename.ldf (여기서 filename은 AttachDBFilename 값으로 지정 된 파일의 이름)을 대신 합니다. 이 변경을 통해 SQL Server 사양에 따라 명명된 로그 파일을 제공하여 디버깅을 개선합니다.|  
|제안 해결 방법|로그 파일 이름은 응용 프로그램에 대 한 중요 한 경우 표준 _log.ldf 파일 이름 형식은 기대 하는 응용 프로그램 업데이트 되어야 합니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName>|  
|분석기|CD0059|  
  
<a name="diagnostic60"></a>   
## <a name="60-pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a>60: Page.LoadComplete 이벤트 System.Web.UI.WebControls.EntityDataSource 컨트롤 데이터 바인딩을 호출을 사용 하면 더 이상  
  
|||  
|-|-|  
|세부 정보|`Page.LoadComplete` 더 이상 이벤트 사용 하면 매개 변수 생성/업데이트/삭제 하는 변경에 대 한 데이터 바인딩을 호출 System.Web.UI.WebControls.EntityDataSource 제어 합니다. 이 변경 내용은 데이터베이스에 대 한 불필요 한 이동 제거 하 고 컨트롤의 값을 재설정 되지 않도록 방지 SqlDataSource 및 ObjectDataSource와 같은 다른 데이터 컨트롤과 일관 된 동작을 생성 합니다. 이러한 변경으로 인해 드물게 응용 프로그램에서 `Page.LoadComplete` 이벤트의 데이터 바인딩 호출을 사용하는 경우 다른 동작이 발생합니다.|  
|제안 해결 방법|데이터 바인딩에 필요한 경우, 수동으로 앞부분의 다시 게시 하는 이벤트에는 databind를 호출 합니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|분석기|CD0060|  
  
<a name="diagnostic61"></a>   
## <a name="61-webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a>61: WebUtility.HtmlDecode 잘못 된 입력된 시퀀스를 더 이상 디코딩  
  
|||  
|-|-|  
|세부 정보|기본적으로 디코딩 메서드는 더 이상 잘못된 입력 시퀀스를 잘못된 UTF-16 문자열로 디코딩하지 않습니다. 대신, 원래 입력을 반환합니다.|  
|제안 해결 방법|문자열에 UTF-16 데이터 대신 이진 데이터를 저장하는 경우에만 디코더 출력에서의 변경 사항이 문제가 되어야 합니다. 이 동작을 명시적으로 제어 하려면 설정는 `aspnet:AllowRelaxedUnicodeDecoding` 특성은 [appSettings](https://msdn.microsoft.com/en-us/library/ms228154\(v=vs.110\).aspx) 요소를 레거시 동작을 사용 하려면 true 또는 false 현재 동작을 사용 하도록 합니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Net.WebUtility.HtmlDecode%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Net.WebUtility.HtmlDecode%28System.String%2CSystem.IO.TextWriter%29?displayProperty=fullName><br /><br /> <xref:System.Net.WebUtility.UrlDecode%28System.String%29?displayProperty=fullName>|  
|분석기|CD0061|  
  
<a name="diagnostic63"></a>   
## <a name="63-apps-published-with-clickonce-that-use-a-sha-256-code-signing-certificate-may-fail-on-windows-2003"></a>63: sha-256 코드 서명 인증서를 사용 하는 ClickOnce로 게시 된 앱은 Windows 2003에서 실패할 수 있습니다  
  
|||  
|-|-|  
|세부 정보|실행 파일이 SHA256으로 서명됩니다. 이전에는 코드 서명 인증서가 SHA-1 또는 SHA-256인지에 관계없이 SHA1로 서명되었습니다. 적용 대상:<br /><br /> Visual Studio 2012 이상으로 빌드된 모든 응용 프로그램<br /><br /> .NET Framework 4.5가 있는 시스템에서 Visual Studio 2010 또는 이전 버전으로 빌드된 응용 프로그램<br /><br /> 또한 .NET Framework 4.5 이상이 있는 경우 컴파일 시의 대상 .NET Framework 버전에 관계없이 ClickOnce 매니페스트도 SHA-256 인증서에 대해 SHA-256으로 서명됩니다.|  
|제안 해결 방법|ClickOnce 실행 파일을 서명 하는 변경 내용에는 Windows Server 2003 시스템을만 영향을 줍니다. KB 938397을 설치 하는 것 필요로 합니다.<br /><br /> 앱이 .NET Framework 4.0 또는 이전 버전을 대상으로 하는 경우에도 SHA-256으로 매니페스트에 서명하는 변경 내용으로 인해 .NET Framework 4.5 이상 버전에서 런타임 종속성이 발생합니다.|  
|범위|Microsoft Edge|  
|버전|4.5-4.6|  
|형식|대상 변경|  
|분석기|CD0063|  
  
<a name="diagnostic68"></a>   
## <a name="68-dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a>68: DbParameter.Precision 및 DbParameter.Scale는 이제 공용 가상 멤버  
  
|||  
|-|-|  
|세부 정보|DbParameter.Precision 및 DbParameter.Scale 공용 가상 속성으로 구현 됩니다. DbParameter.IDbDataParameter.Precision 및 DbParameter.IDbDataParameter.Scale 해당 명시적 인터페이스 구현으로 대체 됩니다.|  
|제안 해결 방법|ADO.NET 데이터베이스 공급자를 다시 작성할 때 이러한 차이 전체 자릿수 및 소수 속성에 적용 될 'override' 키워드가 필요 합니다. 이 경우에 필요; 구성 요소를 다시 작성 기존 이진 파일은 계속 작동 합니다.|  
|범위|사소함|  
|버전|4.5.1|  
|형식|대상 변경|  
|영향을 받는 Api|<xref:System.Data.Common.DbParameter.Precision?displayProperty=fullName><br /><br /> <xref:System.Data.Common.DbParameter.Scale?displayProperty=fullName>|  
|분석기|CD0068|  
  
<a name="diagnostic73"></a>   
## <a name="73-dataobjectgetdata-now-retrieves-data-as-utf-8"></a>73: DataObject.GetData은 이제 u t F-8로 데이터를 검색  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4로 하거나.NET Framework 4.5.1 또는 이전 버전에서 실행 되는 응용 프로그램의 경우 DataObject.GetData는 HTML 형식의 데이터를 ASCII 문자열로 검색 합니다. 그 결과 ASCII 문자가 아닌 문자(ASCII 코드가 0x7F보다 큰 문자)는 임의의 두 문자로 표시됩니다.<br /><br /> .NET Framework 4.5 이상 및.NET Framework 4.5.2에서 실행을 대상으로 하는 앱에 대 한 `DataObject.GetData` 0x7F 보다 큰 문자를 올바르게 나타내는 u t F-8로 HTML 형식의 데이터를 검색 합니다.|  
|제안 해결 방법|(예를 들어 명시적으로 인코딩 함으로써 UTF8Encoding.GetString 메서드에 전달 하 여 클립보드에서 검색 한 HTML 문자열) HTML 형식 문자열 인코딩 문제에 대 한 해결책을 구현 하는 경우 버전 4에서 4.5로에서 응용 프로그램 대상을 해당 해결 방법을 제거 해야 합니다.<br /><br /> 어떤 이유로 이전 동작이 필요한 경우 응용 프로그램에는 해당 결과를 얻으려면.NET Framework 4.0 대상 수 있습니다.|  
|범위|Microsoft Edge|  
|버전|4.5.2|  
|형식|대상 변경|  
|영향을 받는 Api|<xref:System.Windows.DataObject.GetData%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Windows.DataObject.GetData%28System.String%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Windows.DataObject.GetData%28System.Type%29?displayProperty=fullName>|  
|분석기|CD0073|  
  
<a name="diagnostic75"></a>   
## <a name="75-targetframeworkname-for-default-app-domain-no-longer-defaults-to-null-if-not-set"></a>75: TargetFrameworkName 기본 응용 프로그램 도메인에 대 한 더 이상 기본적으로 설정 하지 않으면 null  
  
|||  
|-|-|  
|세부 정보|TargetFrameworkName가 명시적으로 설정 된 않은 경우 기본 응용 프로그램 도메인에서 이전에 null입니다. 4.6부터, 기본 응용 프로그램 도메인에 대 한 TargetFrameworkName 속성 (있는 경우)는 TargetFrameworkAttribute에서 파생 된 기본 값이 포함 됩니다. 기본이 아닌 응용 프로그램 도메인은 명시적으로 재정의 하지 않으면 해당 TargetFrameworkName (4.6에서 null로 기본값은)는 기본 응용 프로그램 도메인에서 상속 하도록 계속 됩니다.|  
|제안 해결 방법|코드에 의존 하지로 업데이트 해야 `AppDomainSetup.TargetFrameworkName` 기본값인 null로 설정 합니다. 필요한 경우는이 속성이 null로 계산을 계속 설정할 수 있습니다 명시적으로 해당 값으로.|  
|범위|Microsoft Edge|  
|버전|4.6|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName>|  
|분석기|CD0075B<br /><br /> CD0075A|  
  
<a name="diagnostic76"></a>   
## <a name="76-x509certificate2tostringbool-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>76: X509Certificate2.ToString(bool) 이제 때.NET 처리할 수 없는 인증서를 throw 하지 않습니다  
  
|||  
|-|-|  
|세부 정보|이전에이 메서드에서 throw 되는 verbose 매개 변수를 't r u e'가 전달 되었고 인증서를 설치한 경우.Net에서 지원 되지 않는 프레임 워크입니다. 이제 메서드는 성공 하 고는 certifiate의 액세스할 수 없는 부분을 생략 하는 유효한 문자열을 반환 합니다.|  
|제안 해결 방법|X509Certificate2.ToString(bool)에 따라 모든 코드는 API 발생 했을 것 이전에 일부 경우에 반환 되는 문자열 일부 인증서 데이터 (예: 공개 키, 개인 키 및 확장)를 제외 시킬 수도 예상 하도록 업데이트 되어야 합니다.|  
|범위|Microsoft Edge|  
|버전|4.6|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString%28System.Boolean%29?displayProperty=fullName>|  
|분석기|CD0076|  
  
<a name="diagnostic77"></a>   
## <a name="77-reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>77: 리플렉션 개체 더 이상 관리 코드에서-out-of-process DCOM 클라이언트로 전달할 수  
  
|||  
|-|-|  
|세부 정보|더이상 리플렉션 개체를 관리 코드에서 out-of-process DCOM 클라이언트로 전달할 수 없습니다. 다음과 같은 영향을 받습니다.<br /><br /> Assembly<br /><br /> MemberInfo (및 해당 파생된 형식, FieldInfo, MethodInfo, 형식 및 형식 정보가 포함)<br /><br /> MethodBody<br /><br /> 모듈<br /><br /> ParameterInfo입니다.<br /><br /> 에 대 한 호출이 `IMarshal` 반환 개체에 대 한 `E_NOINTERFACE`합니다.|  
|제안 해결 방법|마샬링 리플렉션이 아닌 개체를 사용 하는 코드 업데이트|  
|범위|사소함|  
|버전|4.6|  
|형식|런타임|  
|분석기|CD0077|  
  
<a name="diagnostic78"></a>   
## <a name="78-contentdisposition-datetimes-returns-slightly-different-string"></a>78: ContentDisposition 날짜/시간은 약간 다른 문자열을 반환  
  
|||  
|-|-|  
|세부 정보|ContentDispositions의 문자열 표현은 항상 두 자리 날짜/시간의 시 구성 요소를 나타내는 4.6부터 바뀌었습니다. 이 준수 하는 [RFC822](http://www.ietf.org/rfc/rfc0822.txt) 및 [RFC2822](http://www.ietf.org/rfc/rfc2822.txt)합니다. 이 인해 `ContentDisposition.ToString` 문자열을 반환 약간 다른 시나리오에서 4.6에서 오전 10시 전의 처리 시간 요소 중 하나입니다. 참고 ContentDispositions 모든 ContentDisposition ToString 작업, serialization 또는 GetHashCode 호출을 검토 해야 하므로를 문자열로 변환를 통해 serialize 경우가 됩니다.|  
|제안 해결 방법|다른.NET Framework 버전에서 ContentDispositions의 문자열 표현을 서로 올바르게 비교는 기다리지는 않습니다. 가능 하면 비교를 수행 하기 전에 다시 ContentDispositions, 문자열을 변환 합니다.|  
|범위|사소함|  
|버전|4.6|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=fullName><br /><br /> <xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=fullName>|  
|분석기|CD0078|  
  
<a name="diagnostic82"></a>   
## <a name="82-workflowdesignerload-doesnt-remove-symbol-property"></a>82: WorkflowDesigner.Load 기호 속성을 제거 하지 않습니다  
  
|||  
|-|-|  
|세부 정보|WorkflowDesigner.Load() 메서드를 사용 하 여 다시 호스트 된 3.5 워크플로 로드 하 고 워크플로 디자이너에서.NET Framework 4.5를 대상으로 하는 경우는 XamlDuplicateMemberException 워크플로 저장 하는 동안 예외가 발생 합니다.|  
|제안 해결 방법|이 버그를 설정 하 여 해결할 수 수 있도록 워크플로 디자이너에서.NET Framework 4.5를 대상으로 할 때에 나타납니다는 `WorkflowDesigner.Context.Services.GetService<DesignerConfigurationService>().TargetFrameworkName` .NET Framework 4.0에 있습니다.<br /><br /> 또는 사용 하 여 문제를 피할 수 있습니다는 [WorkflowContext.Load(string)](https://msdn.microsoft.com/en-us/library/ee425926\(v=vs.110\).aspx) 대신 워크플로 로드 하는 메서드 [WorkflowDesigner.Load()](https://msdn.microsoft.com/en-us/library/ee403482\(v=vs.110\).aspx)합니다.|  
|범위|주요함|  
|버전|4.5-4.5.2|  
|형식|대상 변경|  
|영향을 받는 Api|<xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=fullName>|  
|분석기|CD0082|  
  
<a name="diagnostic83"></a>   
## <a name="83-sqlconnectionopen-fails-on-windows-7-with-non-ifs-winsock-bsp-or-lsp-present"></a>83: SqlConnection.Open 비 IFS Winsock BSP 또는 LSP가 있는 Windows 7에서 실패 합니다.  
  
|||  
|-|-|  
|세부 정보|비 IFS Winsock BSP 또는 LSP를 사용 하는 Windows 7 컴퓨터에서 실행 중인 컴퓨터에 있는 경우.NET Framework 4.5에서 SqlConneciton.Open 및 OpenAsync 실패 합니다.<br /><br /> 비 IFS BSP 또는 LSP가 설치 되어 있는지를 확인 하려면 사용 된 `netsh WinSock Show Catalog` 명령을 실행 하 고 검사 모든 `Winsock Catalog Provider Entry` 반환 되는 항목입니다. 서비스 플래그 값의 경우는 `0x20000` 비트 집합, 공급자 IFS 핸들을 사용 하 고 올바르게 작동 합니다. 하는 경우는 `0x20000` 설정이 해제 (설정 안 함), 비 IFS BSP 또는 LSP가 있습니다.|  
|제안 해결 방법|이 버그는 하므로.NET Framework를 업그레이드 하 여 방지할 수 있습니다.NET Framework 4.5.2에서에서 수정 되었습니다. 또는 모든 설치 된 비-IFS Winsock Lsp를 제거 하 여 방지할 수 있습니다.|  
|범위|사소함|  
|버전|4.5-4.5.2|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=fullName><br /><br /> <xref:System.Data.SqlClient.SqlConnection.OpenAsync%28System.Threading.CancellationToken%29?displayProperty=fullName>|  
|분석기|CD0083|  
  
<a name="diagnostic84"></a>   
## <a name="84-icommandcanexecutechanged-event-behaviour-changed-in-net-45"></a>84:.NET 4.5에서 ICommand.CanExecuteChanged 이벤트 동작 변경  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.5에는 CanExecuteChangedEvent 이벤트의 보낸 사람에 게 이벤트를 발생 시킨 개체와 동일한 개체가 아닌 경우 무시 되었습니다. 이 버그는.NET Framework 4.5 servcing 업데이트에서 수정 되었습니다.|  
|제안 해결 방법|이 버그는 되었습니다 수정.NET Framework 4.5에서.NET Framework 최신 상태 인지 확인 하 여 또는.NET Framework 4.5.1로 업그레이드 하 여 방지할 수 있도록 릴리스, 서비스를 제공 합니다. 또한 CanExecuteChanged 명령을 발생 시킬 때 보낸 사람에 게 이벤트를 발생 시키는 개체와 동일한 지 확인할 수 있도록 ICommand를 사용 하 여 응용 프로그램 코드를 수정할 수 있습니다.|  
|범위|사소함|  
|버전|4.5-4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=fullName>|  
|분석기|CD0084|  
  
<a name="diagnostic85"></a>   
## <a name="85-some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a>85: 일부.NET Api (처리) 하는 첫 번째 기회 인해 EntryPointNotFoundExceptions  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.5에서 적은 수의.NET 메서드에 EntryPointNotFoundExceptions 첫 번째 기회를 throw 하기 시작 했습니다. 이러한 예외는.Net 내에서 처리 된 Framework 하지만 첫 번째 예외는 예상 하지 않은 테스트 자동화를 손상 시킬 수 있습니다. 이 Api HighVersionLie을 사용 하는 경우 일부 ApiVerifier 시나리오를 중단 합니다.|  
|제안 해결 방법|.NET Framework 4.5.1로 업그레이드 하 여이 버그를 방지할 수 있습니다. 또는 첫 번째 EntryPointNotFoundExceptions에서 중단 되지 테스트 자동화를 업데이트할 수 있습니다.|  
|범위|Microsoft Edge|  
|버전|4.5-4.5.1|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Diagnostics.Debug.Assert%28System.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%2CSystem.String%29?displayProperty=fullName><br /><br /> [Debug.Assert (부울, 문자열, 문자열, 개체\<xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%29?displayProperty=fullName>|  
|분석기|CD0085|  
  
<a name="diagnostic86"></a>   
## <a name="86-scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a>86: WPF TreeView 또는 그룹화 된 목록 상자는 VirtualizingStackPanel에 스크롤 시스템 중단 될 수 있습니다  
  
|||  
|-|-|  
|세부 정보|.NET Framework v4.5 가상화 스택 패널에서 WPF TreeView 스크롤 발생할 수 있습니다 중지에에서 있는 경우 여백을 뷰포트 (사이 있는 항목의 예를 들어, TreeView ItemsPresenter 요소). 또한 일부 경우에 보기에서 다양 한 크기의 항목 수 불안정 여백이 추가 되지 않더라도 합니다.|  
|제안 해결 방법|.NET Framework 4.5.1로 업그레이드 하 여이 버그를 방지할 수 있습니다. 또는 여백은 포함 된 모든 항목은 같은 크기 경우 가상화 된 스택 패널 내에서 컬렉션 (예: Treeview) 보기에서에서 제거할 수 있습니다.|  
|범위|주요함|  
|버전|4.5-4.5.1|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing%28System.Windows.DependencyObject%2CSystem.Boolean%29?displayProperty=fullName>|  
|분석기|CD0086<br /><br /> CD0086|  
  
<a name="diagnostic89"></a>   
## <a name="89-typeisassignablefrom-returns-wrong-result-for-generic-variables-with-constraints"></a>89: Type.IsAssignableFrom 제약 조건이 있는 제네릭 변수에 대 한 잘못 된 결과 반환 합니다.  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.5에서 Type.IsAssignableFrom는 제대로 반환 되지 않는 `false` 일부 제네릭 형식 제약 조건에 대 한 모든 경우에 있습니다.|  
|제안 해결 방법|이 문제는 서비스 업데이트에서 수정 되었습니다. 이 문제를 해결 하려면.NET Framework 4.5 또는.NET Framework 4.5.1로 업그레이드 또는 나중에 업데이트 하십시오. 또는 제네릭 매개 변수에 대 한 제약 조건이 있는 제네릭 형식으로 코드를 사용 하지 마십시오. 리플렉션 Api는 해결 방법으로 사용할 수 있습니다.|  
|범위|사소함|  
|버전|4.5-4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Type.IsAssignableFrom%28System.Type%29?displayProperty=fullName>|  
|분석기|CD0089<br /><br /> CD0089|  
  
<a name="diagnostic91"></a>   
## <a name="91-entityframework-60-loads-very-slowly-in-apps-launched-from-visual-studio"></a>91: entity Framework 6.0을 Visual Studio에서 시작 하는 앱에서 매우 느리게 로드  
  
|||  
|-|-|  
|세부 정보|Entity Framework 6.0을 사용 하 여 Visual Studio 2013에서 응용 프로그램을 시작 하는 것은 매우 느려질 수 있습니다.|  
|제안 해결 방법|이 문제는 entity Framework 6.0.2에서에서 해결 됩니다. 성능 문제를 방지 하려면 entity Framework를 업데이트 하십시오.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|분석기|CD0091|  
  
<a name="diagnostic92"></a>   
## <a name="92-multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a>92: AntiXSSEncoder를 사용 하는 경우 여러 줄 ASP.Net TextBox 간격 변경  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.0에서 추가 줄 사이 삽입 된 줄의 다시 게시 될 여러 줄 텍스트 상자를 사용 하는 경우는 `AntiXSSEncoder`합니다. .NET Framework 4.5에 이러한 여분의 줄 렌더링 되지 않는 포함 하지만 웹 응용 프로그램은.NET 4.5를 대상으로 하는 경우에 해당|  
|제안 해결 방법|수 4.0 웹 응용 프로그램에.NET 4.5 대상이 변경 되거나 더 이상 필요 없는 줄 바꿈을 삽입 하는 향상 된 여러 줄 텍스트 상자에 있을 수 없습니다. 필요 없는 경우에 응용 프로그램.NET Framework 4.0을 대상으로 하 여.NET Framework 4.5에서 실행 하는 경우 이전 동작에 있을 수 있습니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|대상 변경|  
|분석기|CD0092|  
  
<a name="diagnostic95"></a>   
## <a name="95-concurrentqueuettrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>95: ConcurrentQueue<>\>합니다. TryPeek는 out 매개 변수를 통해 잘못 된 null을 반환할 수 있습니다.  
  
|||  
|-|-|  
|세부 정보|몇 가지 다중 스레드 시나리오에서 `ConcurentQueue<T>.TryPeek` true를 반환할 수 있지만 (정확 하 고 미리 본 값)이 아닌 값이 null 인 out 매개 변수를 채웁니다.|  
|제안 해결 방법|이 문제는.NET Framework 4.5.1에서에서 해결 됩니다. 이 프레임 워크를 업그레이드 하면 문제가 해결 됩니다.|  
|범위|주요함|  
|버전|4.5-4.5.1|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek%28%600%40%29?displayProperty=fullName>|  
|분석기|CD0095|  
  
<a name="diagnostic98"></a>   
## <a name="98-multiple-items-in-a-single-tablelayoutpanel-cell-may-be-rearranged"></a>98: 단일 TableLayoutPanel 셀에서 여러 항목을 다시 배열할 수 있습니다  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.5에서 여러 항목 같은 TableLayoutPanel 셀에 배치 됩니다 있습니다 표시 될 수 있습니다 다른 순서에 따라.NET Framework 4.0 보다 합니다.|  
|제안 해결 방법|이 동작은.NET Framework 4.5에 대 한 서비스 업데이트에 되돌려 졌습니다. 이 문제를 해결 하려면.NET Framework 4.5 또는.NET Framework 4.5.1로 업그레이드 또는 나중에 업데이트 하십시오. 또는 같은 TableLayourPanel 셀에 여러 항목의 모호한 경우를 하지 마십시오.|  
|범위|사소함|  
|버전|4.5-4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Windows.Forms.TableLayoutControlCollection.Add%28System.Windows.Forms.Control%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|분석기|CD0098|  
  
<a name="diagnostic100"></a>   
## <a name="100-foreach-iterator-variable-is-now-scoped-within-the-iteration-so-closure-capturing-semantics-are-different-in-c5"></a>100: Foreach 반복기 변수 현재 범위는 반복 내에서 closure 캡처링 의미 체계는 다르게 (C#&5;)  
  
|||  
|-|-|  
|세부 정보|C# 5 (Visual Studio 2012)부터, foreach 반복기 변수는 반복 내에서 범위가 지정 됩니다. 나누기 코드 변수는 foreach closure에 포함 되지를 느끼고 이전에 발생할 수 있습니다. 이러한 변경의 증상 반복기 변수는 delagate에 전달 된 대리자가 호출 될 때 원래의 값 대신 대리자를 만든 시간에 원래의 값으로 간주 되며 됩니다.|  
|제안 해결 방법|이상적으로 새로운 컴파일러 동작의 결과 코드를 업데이트 해야 합니다. 이전 의미 체계가 필요한 경우 루프의 범위 외부에서 명시적으로 배치 되는 별도 변수로 반복기 변수를 대체할 수 있습니다.|  
|범위|주요함|  
|버전|4.5|  
|형식|대상 변경|  
|분석기|CD0100|  
  
<a name="diagnostic101"></a>   
## <a name="101-htmltextwriter-does-not-render-br-element-correctly"></a>101: HtmlTextWriter 렌더링 하지 않습니다\`<br>\>' 요소 올바르게  
  
|||  
|-|-|  
|세부 정보|호출 하는.NET Framework 4.6부터 `HtmlTextWriter.RenderBeginTag()` 및 `HtmlTextWriter.RenderEndTag()` 와 `<BR />` 요소는 하나만 삽입 올바르게 `<BR />` (대신 2 개)|  
|제안 해결 방법|앱 추가에 의존 하는 경우 `<BR />` 태그 `HtmlTextWriter.RenderBeginTag()` 를 두 번 호출 해야 합니다. 이 문제를 변경 하는 또 다른 옵션은 이전 버전의 동작을 얻기 위해 이전 버전의.NET Framework를 대상으로 하므로.NET Framework 4.6을 대상으로 하는 응용 프로그램을만 영향을 줍니다.|  
|범위|Microsoft Edge|  
|버전|4.6|  
|형식|대상 변경|  
|영향을 받는 Api|<xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName>|  
|분석기|CD0101|  
  
<a name="diagnostic104"></a>   
## <a name="104-calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>104: 호출 Items.Refresh WPF ListBox, ListView, 또는 선택 된 항목이 포함 된 DataGrid에 중복 항목이 요소에 표시 될 수 있습니다  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.5 ListBox.Items.Refresh 코드에서 호출 하는 ListBox에서 항목을 선택 하는 동안 선택한 항목 목록에서 중복을 발생할 수 있습니다. ListView DataGrid와 유사한 문제가 발생 합니다. 이.NET Framework 4.6에서 해결 됩니다.|  
|제안 해결 방법|프로그래밍 방식으로 새로 고침을 호출 하기 전에 항목의 선택을 취소 한 다음 호출이 완료 된 후에 다시 선택 하 여이 문제를 해결할 수 있습니다. 또는이 문제는.NET Framework 4.6에서 수정 되었습니다 하 고.NET Framework의 해당 버전을 업그레이드 하 여 해결 될 수도 있습니다.|  
|범위|사소함|  
|버전|4.5-4.6|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName>|  
|분석기|CD0104|  
  
<a name="diagnostic105"></a>   
## <a name="105-etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a>105: ETW EventListeners 명시적 키워드 (예: TPL 공급자)와 공급자의 이벤트를 캡처하지 않습니다  
  
|||  
|-|-|  
|세부 정보|빈 키워드 마스크 ETW EventListeners 제대로 명시적 키워드와 공급자의 이벤트를 캡처하지 않습니다. .NET Framework 4.5에는 TPL 공급자 명시적 키워드를 제공 하기 시작 했 고이 문제를 트리거됩니다. .NET Framework 4.6 EventListeners이이 문제를 더 이상 업데이트 되었습니다.|  
|제안 해결 방법|이 문제를 해결 하려면 명시적으로 사용 하 여 "키워드" 마스크를 지정 하는 EnableEvents 오버 로드를 호출 하 여 EnableEvents (eventSource, 수준) 호출을 바꾸는: `EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))`합니다.<br /><br /> 또는이 문제는.NET Framework 4.6에서 수정 되었습니다 하 고.NET Framework의 해당 버전을 업그레이드 하 여 해결 될 수도 있습니다.|  
|범위|Microsoft Edge|  
|버전|4.5-4.6|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%29?displayProperty=fullName>|  
|분석기|CD0105|  
  
<a name="diagnostic109"></a>   
## <a name="109-building-an-entity-framework-edmx-with-visual-studio-2013-can-fail-with-error-msb4062-if-using-the-entitydeploysplit-or-entityclean-tasks"></a>109: Visual Studio 2013과 Entity Framework edmx 구축 수 오류로 인해 실패 MSB4062 EntityDeploySplit 또는 EntityClean 작업을 사용 하는 경우  
  
|||  
|-|-|  
|세부 정보|Msbuild 파일 위치, 유효 하지 않은 것 이전 Entity Framework 대상 파일을 일으키는 변경 하는 MSBuild 12.0 도구 (Visual Studio 2013에 포함). 결과 있는 `EntityDeploySplit` 및 `EntityClean` 를 찾을 수 없기 때문에 실패 한 작업이 `Microsoft.Data.Entity.Build.Tasks.dll`합니다. 이 줄 바꿈으로 도구 집합 (msbuild/VS) 변경 되지 않는.NET Framework 변경으로 인해 참고 합니다. 단순히.NET Framework를 업그레이드할 때가 아니라 개발자 도구를 업그레이드 하는 경우에 발생 합니다.|  
|제안 해결 방법|Entity Framework 대상 파일은.NET Framework 4.6의 새로운 msbuild 레이아웃 기능인 작업할 고정 됩니다. 해당 버전의 Framework로 업그레이드 하면이 문제를 해결 됩니다. 또는 [이](http://stackoverflow.com/a/24249247/131944) 해결 방법은 대상 파일을 직접 패치 데 사용할 수 있습니다.|  
|범위|주요함|  
|버전|4.5.1-4.6|  
|형식|대상 변경|  
|분석기|CD0109|  
  
<a name="diagnostic111"></a>   
## <a name="111-xsd-schema-validation-now-correctly-detects-violations-of-unique-constraints-if-compound-keys-are-used-and-one-key-is-empty"></a>111: 복합 키를 사용 하 고 하나의 키가 비어 있는지 올바르게 XSD 스키마 유효성 검사는 이제 unique 제약 조건 위반 검색  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.6 이전 버전에 복합 키에 대해 unique 제약 조건 키 중 하나가 비어 있으면 검색 하지 XSD 유효성 검사를 발생 시킨 버그를 했습니다. .NET Framework 4.6이이 문제는 해결 되었습니다. 이렇게 하면 보다 정확한 유효성 검사에 있지만 해야 이전에 검사 되지 않은 XML에도 발생할 수 있습니다.|  
|제안 해결 방법|이보다, 하는 경우.NET Framework 4.0 유효성 검사가 필요, 유효성을 검사 하는 응용 프로그램 버전 4.5 (또는 이전)를 대상.NET Framework의 합니다. 하지만.NET 4.6을 대상 변경 하는 경우는 중복 된 복합 키 (설명한이 문제 설명에) 되지 않는 유효성을 검사 해야 하는 코드 검토를 수행 해야 합니다.|  
|범위|Microsoft Edge|  
|버전|4.6|  
|형식|대상 변경|  
|분석기|CD0111|  
  
<a name="diagnostic112"></a>   
## <a name="112-calling-attributegetcustomattributes-on-an-indexer-property-no-longer-throws-ambiguousmatchexception-if-the-ambiguity-can-be-resolved-by-indexs-type"></a>112: 호출 Attribute.GetCustomAttributes 인덱서 속성에 더 이상 throw AmbiguousMatchException 인덱스의 형식에서 모호성을 해결할 수 없습니다  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.6 호출 하기 전에 `GetCustomAttribute(s)` 인덱서에서 인덱스의 형식만 다른 속성에서 다른 속성인 결과적으로 `AmbiguousMatchException`합니다. .NET Framework 4.6부터 속성의 특성 올바르게 반환 됩니다.|  
|제안 해결 방법|GetCustomAttribute(s) 정상적으로 작동 합니다 더 자주 유의 합니다. 응용 프로그램가 이전에 의존 하는 경우는 `AmbiguousMatchException`, 리플렉션을 사용 하 여 명시적으로 찾기 위해 여러 인덱서 대신 이제 해야 합니다.|  
|범위|Microsoft Edge|  
|버전|4.6|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Attribute.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName>|  
|분석기|CD0112|  
  
<a name="diagnostic113"></a>   
## <a name="113-intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a>113: 일시적으로 (예: ListBox 및 DataGrid) ItemsControls에서 하위 항목으로 스크롤할 수 없음 사용자 지정 Datatemplate을 사용 하는 경우  
  
|||  
|-|-|  
|세부 정보|일부 경우에.NET Framework 4.5의 버그 때문에 발생 했습니다 (예: ListBox, ComboBox, DataGrid, 등) ItemsControls 하지 스크롤 아래 항목을 사용자 지정 Datatemplate을 사용 하는 경우. 스크롤 (스크롤한 후에 백업)를 두 번 비교를 시도 하는 경우 다음 작동 합니다.|  
|제안 해결 방법|이 문제는.NET Framework 4.5.2에서에서 수정 되었습니다 및.NET Framework의 해당 버전 (또는 이후 버전)로 업그레이드 하 여 해결 될 수도 있습니다. 또는 사용자가 이러한 컬렉션의 마지막 항목에 스크롤 막대를 끌어 여전히 수 있지만 두 번로 성공적으로 업그레이드 하려고 할 수 있습니다.|  
|범위|사소함|  
|버전|4.5-4.5.2|  
|형식|런타임|  
|분석기|CD0113|  
  
<a name="diagnostic114"></a>   
## <a name="114-glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-45"></a>114: GlyphRun.ComputeInkBoundingBox() 및 FormattedText.Extent.NET 4.5 부터는 다른 값을 반환 합니다.  
  
|||  
|-|-|  
|세부 정보|향상 되었습니다 GlyphRun.ComputeInkBoundingBox() 및 문제를 해결 하는.NET Framework 4.5에서 FormattedText.Extent 상자 있던 경우에 따라.NET Framework 4.0에 포함 된 문자 모양이에 비해 너무 작습니다. 결과적으로 일부 경계 상자 UI 레이아웃에 약간의 차이가 발생 하는.NET Framework 4.5에 더 큰 시작 됩니다.|  
|제안 해결 방법|주의 몇 가지 문자 모양의 경계 상자 크기 증가 했습니다. 프레젠테이션 및 상자 적중된 테스트에 일반적으로 이러한 변경 내용은 높아집니다 하지만 이전 (전.NET 4.5) 동작이 필요한 경우, 그 수 수 옵트인 app.config 파일에 다음 항목을 추가 하 여:<br /><br /> `<appsettings> <add key="IncludeAllInkInBoundingBox" value="false"> </appsettings>`|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=fullName><br /><br /> <xref:System.Windows.Media.FormattedText.Extent?displayProperty=fullName>|  
|분석기|CD0114|  
  
<a name="diagnostic124"></a>   
## <a name="124-calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a>124: CellEditEnding 처리기에서 호출 DataGrid.CommitEdit 포커스를 삭제 합니다.  
  
|||  
|-|-|  
|세부 정보|DataGrid의 CellEditEnding 이벤트 처리기 중 하나에서 DataGrid.CommitEdit를 호출 하면 포커스를 잃고 DataGrid 합니다.|  
|제안 해결 방법|이 버그는 하므로.NET Framework를 업그레이드 하 여 방지할 수 있습니다.NET Framework 4.5.2에서에서 수정 되었습니다. 또는 명시적으로 CommitEdit를 호출한 후에 다시 DataGrid을 선택 하 여 방지할 수 있습니다.|  
|범위|Microsoft Edge|  
|버전|4.5-4.5.2|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName><br /><br /> <xref:System.Windows.Controls.DataGrid.CommitEdit%28System.Windows.Controls.DataGridEditingUnit%2CSystem.Boolean%29?displayProperty=fullName>|  
|분석기|CD0124|  
  
<a name="diagnostic125"></a>   
## <a name="125-aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a>125: ASP.NET MVC는 이제 경로 매개 변수를 통해 전달 된 문자열에 있는 공백은 이스케이프  
  
|||  
|-|-|  
|세부 정보|RFC 2396에 따르려면 경로에서 작업 매개 변수를 채울 때 경로 경로의 공백은 이스케이프 이제 됩니다. 따라서 반면 `/controller/action/some data` 경로 일치 이전에 `/controller/action/{data}` 제공 `some data` 데이터 매개 변수로 제공 이제는 `some%20data` 대신 합니다.|  
|제안 해결 방법|경로에서 문자열 매개 변수를 이스케이프 해제 하려면 코드를 업데이트 해야 합니다. 필요 하다 고 원래 URI Request.RequestUri.OriginalString API를 통해 액세스할 수 있습니다.|  
|범위|사소함|  
|버전|4.5.2|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Web.Http.RouteAttribute.%23ctor%28System.String%29?displayProperty=fullName>|  
|분석기|CD0125|  
  
<a name="diagnostic127"></a>   
## <a name="127-vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a>127: VB.NET System.Windows Api에 대 한 일부 네임 스페이스 한정자를 더 이상 지원  
  
|||  
|-|-|  
|세부 정보|.NET 4.5.2부터, VB.NET 프로젝트는 System.Windows Api 부분적으로 정규화 된 네임 스페이스를 지정할 수 없습니다. 예를 들어 가리키는 `Windows.Forms.DialogResult` 실패 합니다. 대신, 코드 정규화 된 이름을 참조 해야 합니다 (`System.Windows.Forms.DialogResult`) 또는 특정 네임 스페이스 키를 가져오고에 단순히 참조 `DialogResult`합니다.|  
|제안 해결 방법|참조 하도록 코드를 업데이트 해야 `System.Windows` Api 간단한 이름 (및 관련 네임 스페이스 가져오기) 또는 정규화 된 이름입니다.|  
|범위|사소함|  
|버전|4.5.2|  
|형식|대상 변경|  
|분석기|CD0127|  
  
<a name="diagnostic129"></a>   
## <a name="129-two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a>129: public이 아닌 setter 사용 하 여 속성에 양방향 데이터 바인딩을 지원 되지 않습니다  
  
|||  
|-|-|  
|세부 정보|공용 속성에 데이터 바인딩 하려고 적이 시나리오는 지원된 합니다. 이 시나리오는.NET Framework 4.5.1 부터는 InvalidOperationException을 throw 합니다. 이 새만 예외가 구체적으로.NET Framework 4.5.1을 대상으로 하는 응용 프로그램에 유의 합니다. 응용 프로그램에서.NET Framework 4.5를 대상으로 하는 경우 호출이 허용 됩니다. 응용 프로그램에는 특정.NET Framework 버전 대상 하지 않는, 바인딩이 단방향으로 처리 됩니다.|  
|제안 해결 방법|단방향 바인딩을 사용 하거나 속성의 setter를 공개적으로 노출 하는 응용 프로그램 업데이트 되어야 합니다. 또는.NET Framework 4.5를 대상으로 지정 하면 응용 프로그램에서 이전 동작을 노출 합니다.|  
|범위|사소함|  
|버전|4.5.1|  
|형식|대상 변경|  
|영향을 받는 Api|<xref:System.Windows.Data.BindingMode?displayProperty=fullName>|  
|분석기|CD0129|  
  
<a name="diagnostic130"></a>   
## <a name="130-marshalsizeof-and-marshalptrtostructure-overloads-break-dynamic-code"></a>130: Marshal.SizeOf와 Marshal.PtrToStructure 오버 로드 나누기 동적 코드  
  
|||  
|-|-|  
|세부 정보|메서드를 동적으로 바인딩.NET Framework 4.5.1 부터는 `Marshal.SizeOf` 또는 `Marshal.PtrToStructure` (Windows PowerShell, IronPython, 예를 들어 C# dynamic 키워드를 통해) 발생할 수 있습니다 `MethodInvocationExceptions` 스크립팅 엔진에 모호한 될 수 있는 이러한 메서드의 새 오버 로드에 추가 된 없기 때문에 있습니다.|  
|제안 해결 방법|사용 하는 오버 로드 먼저를 명확히 표시 하는 스크립트를 업데이트 합니다. 일반적으로와 메서드의 형식 매개 변수를 명시적으로 캐스팅 하 여 작업 수행이 있습니다 `System.Type`합니다. 참조 [이 링크](https://support.microsoft.com/en-us/kb/2909958/) 자세한 세부 정보 및 문제 해결 하는 방법의 예입니다.|  
|범위|사소함|  
|버전|4.5.1|  
|형식|런타임|  
|분석기|CD0130|  
  
<a name="diagnostic131"></a>   
## <a name="131-previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a>131: PreviewLostKeyboardFocus 반복적으로 호출 하는 처리기는 Windows Forms 메시지 상자를 표시 하는 경우  
  
|||  
|-|-|  
|세부 정보|호출 하는.NET Framework 4.5부터 `System.Windows.Forms.MessageBox.Show` 에서 `UIElement.PreviewLostKeyboardFocus` 처리기는 처리기를 다시 발생 메시지 상자를 닫을 때의 메시지 상자는 무한 루프에 발생 합니다.|  
|제안 해결 방법|-이 문제를 해결 하는 방법은 두 가지가<br /><br /> 호출 하 여이 피할 수 있습니다 `System.Windows.MessageBox.Show` 대신 `System.Windows.Forms.MessageBox.Show`합니다.<br /><br /> 메시지 상자를 표시 하 여이 피할 수 있습니다는 `LostKeyboardFocus` 이벤트 처리기 (반대인는 `PreviewLostKeyboardFocus` 이벤트 처리기).|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=fullName>|  
|분석기|CD0131|  
  
<a name="diagnostic133"></a>   
## <a name="133-a-concurrentdictionary-serialized-in-net-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-451-or-452"></a>133: ConcurrentDictionary NetDataContractSerializer 포함 된.NET 4.5에서 serialize.NET 4.5.1 또는 4.5.2에서 역직렬화 할 수 없습니다  
  
|||  
|-|-|  
|세부 정보|이 형식에는 내부 변경 내용으로 인해 `System.Collections.Concurrent.ConcurrentDictionary` .NET Framework 4.5를 사용 하 여 serialize 되는 개체를 사용 하는 `NetDataContractSerializer` .NET Framework 4.5.2 또는.NET Framework 4.5.1에서에서 역직렬화 할 수 없습니다.<br /><br /> 그 반대로 이동 참고 (.NET Framework와 함께 직렬화 4.5.x 및.NET Framework 4.5가 역직렬화) 작동 합니다. 마찬가지로,.NET Framework 4.6 모든 4.x 버전 간 serialization이 작동 합니다.<br /><br /> 직렬화 및 역직렬화 단일 버전의.NET Framework와 영향을 받지 않습니다.|  
|제안 해결 방법|Serialize 하 고.NET Framework 4.5와.NET Framework 4.5.1/4.5.2 사이의 ConcurrentDictionary deserialize 하는 데 필요한 경우 NetDataContractSerializer 대신 DataContractSerializer 또는 BinaryFormatter serializer와 같은 경우 대체 serializer는 사용 해야 합니다.<br /><br /> 또는.NET Framework 4.6에서이 문제를 처리 하기 때문에.NET Framework의 해당 버전을 업그레이드 하 여 해결할 수 있습니다.|  
|범위|사소함|  
|버전|4.5.1-4.6|  
|형식|런타임|  
|분석기|CD0133|  
  
<a name="diagnostic134"></a>   
## <a name="134-persian-calendar-now-uses-the-hijri-solar-algorithm"></a>134: 페르시아력을 지금 사용 하 여 회교식 양력 알고리즘  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.6 부터는 PersianCalendar 클래스는 회교식 양력 알고리즘을 사용 합니다. 날짜는 PersianCalendar와 다른 일정 간에 변환할 2023 (그레고리오 력) 보다 이후 이거나 1800 보다 이전 날짜에 대 한.NET Framework 4.6로 시작 하는 약간 다른 결과 생성할 수 있습니다.<br /><br /> 또한 `PersianCalendar.MinSupportedDateTime` 이제 `March 22, 0622 instead of March 21, 0622`합니다.|  
|제안 해결 방법|일부 초기 또는 늦은 날짜는 PersianCalendar.NET 4.6에서 사용 하는 경우에 약간 다른 줄 수 있습니다. 수 있습니다. 또한 서로 다른.NET Framework 버전에서 실행할 수 있는 프로세스 사이의 날짜를 직렬화 할 때 저장 하지 마십시오을 PersianCalendar 날짜 문자열로 (하므로 이러한 값은 다 수 있습니다).|  
|범위|사소함|  
|버전|4.6|  
|형식|런타임|  
|영향을 받는 Api|<xref:System.Globalization.PersianCalendar?displayProperty=fullName>|  
|분석기|CD0134|  
  
<a name="diagnostic138"></a>   
## <a name="138-calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a>138: null 인수를 가진 호출 CreateDefaultAuthorizationContext 바뀌었습니다.  
  
|||  
|-|-|  
|세부 정보|AuthorizationContext의 구현에 대 한 호출에서 반환 되는 `CreateDefaultAuthorizationContext(IList<IAuthorizationPolicy>)` 인수 null authorizationPolicies와.NET Framework 4.6의 구현이 변경 되었습니다.|  
|제안 해결 방법|드문 경우이지만 사용자 지정 인증을 사용하는 WCF 앱은 다르게 동작할 수 있습니다. 이 경우 두 가지 방법 중 하나로 이전 동작을 복원할 수 있습니다.<br /><br /> 4.6 이전 버전의 .NET Framework를 대상으로 사용하도록 앱을 다시 컴파일합니다. IIS 호스팅 서비스를 사용 하 여는 <httpRuntime targetframework="x.x"></httpRuntime> \> 요소는 이전 버전의.NET Framework를 대상으로 합니다.<br /><br /> 다음 줄을 추가 하는 `<appSettings>` app.config 파일의 섹션:`<add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />`|  
|범위|사소함|  
|버전|4.6|  
|형식|대상 변경|  
|영향을 받는 Api|<xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29?displayProperty=fullName>|  
|분석기|CD0138|  
  
<a name="diagnostic141"></a>   
## <a name="141-wpf-treeviewitem-must-be-used-within-a-treeview"></a>141: TreeView에서 TreeViewItem WPF를 사용 해야  
  
|||  
|-|-|  
|세부 정보|변경 내용은 외부 TreeView에서 TreeViewItem 요소의 사용을 제한 하는 4.5에서 도입 되었습니다. 이러한 쿼리는 다음과 같은 경우:<br /><br /> TreeViewItem의 시각적 부모 패널 아닙니다. (TreeView에 대해 생성 된 TreeViewItem 해야 패널 부모)<br /><br /> TreeViewItem 역할 (ListBox, DataGrid, ListView 등) 목록 컨트롤에 대 한 "항목 호스트"을 VirtualizingStackPanel의 하위 항목입니다. 가상화를 사용할 필요가 없습니다.<br /><br /> VirtualizingStackPanel은 항목 스크롤 (`ScrollUnit="Item"`).<br /><br /> 호출 `VirtualizingStackPanel.MakeVisible(v)` 요소 스크롤해야 `v` 보기에 있습니다. 이렇게 명시적으로 또는 암시적으로 여러 가지 방법으로; 아마도 가장 일반적인 방식으로 간단히 클릭 하면 `v` 키보드 포커스를 부여 합니다.<br /><br /> visual 부모 체인 `v` VirtualizingStackPanel 통과 TreeViewItem 합니다.<br /><br /> 즉, 외부은 TreeView에서 TreeViewItem 사용 되 고 TreeViewItem 보기의 하위 항목을 클릭할 때 표시 됩니다. TreeViewItem에 포커스를 받을 수 하위 항목이 없는 경우이 문제가 되지 표시 됩니다. 이 적중 될 경우의 예는 TreeViewItem DataTemplate의 루트 경우입니다.  이 문제에 도달 하면 WPF 프레임 워크 내에서 발생 하는 InvalidCastException 됩니다.|  
|제안 해결 방법|핫픽스 사용 가능 하 게이 있습니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|분석기|CD0141|  
  
<a name="diagnostic143"></a>   
## <a name="143-x509certificateclaimsetfindclaims-considers-all-claimtypes"></a>143: X509CertificateClaimSet.FindClaims 모든 claimTypes 고려  
  
|||  
|-|-|  
|세부 정보|앱에서 4.6.1,.NET Framework를 대상으로 하는 경우 클레임 집합의 SAN 필드에 여러 DNS 항목을 포함 하는 인증서에서 초기화 되는 X509 FindClaims 메서드 하려고 claimType 인수 모든 DNS 항목과 일치 합니다.<br /><br /> 이전 버전의.NET Framework를 대상으로 하는 응용 프로그램의 경우 FindClaims 메서드는 마지막 DNS 항목에만 claimType 인수와 일치 하도록 시도 합니다.|  
|제안 해결 방법|이 변경은 4.6.1.NET Framework를 대상으로 하는 응용 프로그램을만 영향을 줍니다. 이 변경 내용은 비활성화 될 수 있습니다 (경우에 사용할 수 또는 대상으로 하는 사전&4;.6.1)와 [DisableMultipleDNSEntries](https://msdn.microsoft.com/en-us/library/mt620030%28v=vs.110%29.aspx) 호환성 스위치입니다.|  
|범위|사소함|  
|버전|4.6.1|  
|형식|대상 변경|  
|영향을 받는 Api|<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%28System.String%2CSystem.String%29?displayProperty=fullName>|  
|분석기|CD0143|  
  
<a name="diagnostic144"></a>   
## <a name="144-applicationfiltermessage-no-longer-throws-for-re-entrant-implementations-of-imessagefilterprefiltermessage"></a>144: Application.FilterMessage IMessageFilter.PreFilterMessage 재진입 구현에 대해 더 이상 throw  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.6.1 이전 또는 호출 하는 IMessageFilter.PreFilterMessage와 Application.FilterMessage 어떤 호출된 AddMessageFilter RemoveMessageFilter Application.DoEvents 호출) 하는 것 (동안는 IndexOutOfRangeException 발생 합니다.<br /><br /> 4.6.1.NET Framework를 대상으로 하는 응용 프로그램부터이 예외는 더 이상 throw, 하며 재진입 필터 위에서 설명한 것 처럼 사용할 수 없습니다.|  
|제안 해결 방법|위에서 설명한 재진입 IMessageFilter.PreFilterMessage 동작에 대 한 그 Application.FilterMessage 더 이상 throw는 수입니다. 이 4.6.1.NET Framework를 대상으로 하는 응용 프로그램을만 영향을 줍니다.<br /><br /> 4.6.1.NET Framework를 대상으로 하는 앱을 옵트아웃할 수 있습니다이 변경 (또는 앱에서 이전 프레임 워크를 대상으로 선택할 수 있습니다)를 사용 하 여는 [DontSupportReentrantFilterMessage](https://msdn.microsoft.com/en-us/library/mt620032%28v=vs.110%29.aspx) 호환성 스위치입니다.|  
|범위|Microsoft Edge|  
|버전|4.6.1|  
|형식|대상 변경|  
|영향을 받는 Api|<xref:System.Windows.Forms.Application.FilterMessage%28System.Windows.Forms.Message%40%29?displayProperty=fullName>|  
|분석기|CD0144|  
  
<a name="diagnostic145"></a>   
## <a name="145-currentculture-is-not-preserved-across-wpf-dispatcher-operations"></a>145: CurrentCulture WPF 발송자 작업 간에 유지 되지 않습니다  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.6부터, CurrentCulture 또는 CurrentUICulture 변경 내는 [발송자](https://msdn.microsoft.com/en-us/library/system.windows.threading.dispatcher%28v=vs.110%29.aspx) 발송자 작업이 끝날 때 손실 됩니다. 마찬가지로, CurrentCulture 또는 발송자 작업 외부에서 발생 하는 리소스에 변경 내용이 반영 되지 않을 때 작업이 실행 되 합니다.<br /><br /> 함에도 즉, CurrentCulture 및 CurrentUICulture 변경 WPF UI 콜백 및 WPF 응용 프로그램의 다른 코드 간의 흐르지 않을 수 있습니다.<br /><br /> 변경으로 인해이 [ExecutionContext](https://msdn.microsoft.com/en-us/library/system.threading.executioncontext%28v=vs.110%29.aspx) 원인인 CurrentCulture 및 CurrentUICulture.NET Framework 4.6을 대상으로 하는 앱과 함께 시작 하는 실행 컨텍스트에에서 저장 됩니다. WPF 디스패처 작업 작업을 시작 하 고 작업이 완료 되 면 이전 컨텍스트로 복원 하는 데 사용 되는 실행 컨텍스트를 저장 합니다. CurrentCulture 및 CurrentUICulture 이제의 일부 이므로 해당 컨텍스트를 발송자 작업 내에서 변경 작업을 외부에서 유지 되지 않습니다.|  
|제안 해결 방법|CurrentUICulture 필드에, 모든 발송자 작업에서 검사 활동해왔습니다 UI 이벤트 콜백 처리기) (포함 올바른 CurrentCulture 및 CurrentUICulture 설정 또는 앱이이 변경 내용의 영향을 원하는 CurrentCulture를 저장 하 여 주위 작동 될 수 있습니다. 또는 ExecutionContext 내부 변경 때문에.NET Framework 4.6 이상을 대상으로 앱에만 영향을 줍니다이 WPF 변경,.NET Framework 4.5.2를 대상으로 하 여이 줄 바꿈으로 방지할 수 있습니다.|  
|범위|사소함|  
|버전|4.6|  
|형식|대상 변경|  
|분석기|CD0145|