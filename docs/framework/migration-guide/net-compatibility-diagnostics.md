---
title: ".NET 호환성 진단 | Microsoft 문서"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e481270-b62a-4cb4-8dda-5b4c5b59d61d
caps.latest.revision: 7
author: twsouthwick
ms.author: tasou
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 19006cc5f24ffc66b92e53e8174c6bd33c249679
ms.openlocfilehash: 06ebf87e02c8fd745d9c2f3a55eca329323a7d91
ms.contentlocale: ko-kr
ms.lasthandoff: 05/22/2017

---
# <a name="net-compatibility-diagnostics"></a>.NET 호환성 진단
.NET 호환성 진단은 .NET Framework 버전 간에 응용 프로그램 호환성 문제를 식별할 수 있도록 하는 Roslyn 기반 분석기입니다. 이 목록은 사용할 수 있는 모든 분석기를 포함하지만, 한 하위 집합은 특정 마이그레이션에만 적용됩니다. 분석기는 예정된 마이그레이션에 적용되는 문제를 확인하고 해당 문제만 표시합니다. 영향을 받은 버전별 분할 문제에 대한 내용은 [응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility.md)을 참조하십시오.  
  
 각 문제는 다음과 같은 정보를 포함합니다.  
  
-   이전 버전에서 변경된 내용에 대한 설명입니다.  
  
-   해당 제안 해결 방법은 변경 내용이 고객에 미치는 영향 및 버전 간 호환성을 유지하기 위한 사용할 수 있는 해결 방법의 여부에 대한 설명입니다.  
  
-   변경 내용의 중요성에 대한 평가입니다. 응용 프로그램 호환성 문제는 다음과 같이 분류됩니다.  
  
    |||  
    |-|-|  
    |주요함|다수의 앱에 영향을 주거나 코드를 대폭 수정해야 하는 중요한 변경 내용입니다.|  
    |사소함|소수의 앱에 영향을 주거나 코드를 약간만 수정해야 하는 변경 내용입니다.|  
    |특별한 경우|매우 특별하고 일반적이지 않은 시나리오의 앱에 영향을 주는 변경 내용입니다.|  
    |투명|응용 프로그램 개발자나 사용자에게 뚜렷한 영향을 주지 않는 변경 내용입니다.|  
  
-   버전은 변경 내용이 프레임워크에 처음 표시될 때를 나타냅니다. 일부 변경 내용이 되돌려지고 되돌려진 내용 표시됩니다.  
  
-   변경 형식:  
  
    |||  
    |-|-|  
    |대상 변경|새 버전의 .NET Framework를 대상으로 다시 컴파일되는 앱에 변경 내용이 적용됩니다.|  
    |런타임|이전 버전의 .NET Framework를 대상으로 하지만 이후 버전에서 실행되는 기존 앱에 변경 내용이 적용됩니다.|  
  
-   영향을 받는 API입니다(있는 경우).  
  
-   사용 가능한 진단의 ID  
  
<a name="diagnostic1"></a>   
## <a name="1-soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a>1: SoapFormatter는 해시 테이블과 순서가 지정된 유사 컬렉션 개체를 역직렬화할 수 없습니다  
  
|||  
|-|-|  
|세부 정보|SoapFormatter는 하나의 .NET Framework 버전에서 직렬화된 개체가 다른 버전에서 성공적으로 역직렬화하는 것을 보장하지 않습니다. 특히, 일부 순서가 지정된 컬렉션(예: Hashtable)은 4.0 및 4.5 간에 멤버가 추가되었으며 이러한 형식의 개체가 .NET 4.5로 직렬화된 경우 .NET 4.0으로 역직렬화할 수 없습니다. 직렬화된 데이터가 같은 .NET Framework 버전으로 직렬화 및 역직렬화되면 문제가 발생하지 않습니다.|  
|제안 해결 방법|SoapFormatter 직렬화는 BinaryFormatter 직렬화 또는 NetDataContractSerialization로 대체되어야 .NET Framework 변경 내용에 유연합니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize%28System.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize%28System.IO.Stream%2CSystem.Runtime.Remoting.Messaging.HeaderHandler%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize%28System.IO.Stream%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize%28System.IO.Stream%2CSystem.Object%2CSystem.Runtime.Remoting.Messaging.Header%5B%5D%29?displayProperty=fullName>|  
|분석기|CD0001B<br /><br /> CD0001A|  
  
<a name="diagnostic3"></a>   
## <a name="3-wpf-datatemplate-elements-are-now-visible-to-uia"></a>3: WPF DataTemplate 요소가 UIA에 표시됩니다  
  
|||  
|-|-|  
|설명|이전에는 DataTemplate 요소가 UI 자동화에 표시되지 않았습니다. 4.5부터는 UI 자동화가 이러한 요소를 감지합니다. 이것은 대부분의 사례에 유용하지만 DataTemplate 요소를 포함하지 않는 UIA 트리에 의존하는 테스트를 중단시킬 수 있습니다.|  
|제안 해결 방법|이 응용 프로그램에 대한 UI 자동화 테스트는 이전에 보이지 않던 DataTemplate 요소를 포함하는 UIA 트리에 대해 업데이트가 필요할 수 있습니다. 예를 들어 일부 요소가 서로 옆에 있도록 예상하는 테스트는 이제 이전에 요소 간에 보이지 않던 UIA 요소를 예상해야 할 수 있습니다. 또는 UIA 요소에 대한 특정 개수 또는 인덱스를 사용하는 테스트는 새 값으로 업데이트해야 할 수 있습니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Windows.DataTemplate.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Windows.DataTemplate.%23ctor%28System.Object%29?displayProperty=fullName>|  
|분석기|CD0003|  
  
<a name="diagnostic4"></a>   
## <a name="4-wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a>4: 텍스트 상자가 비활성일 때 WPF TextBox가 선택한 텍스트는 다른 색깔로 표시됩니다  
  
|||  
|-|-|  
|세부 정보|.NET 4.5에서 WPF 텍스트 상자 컨트롤이 비활성일 때(포커스 없음) 상자 안의 선택된 텍스트가 컨트롤이 활성화될 때와 다른 색으로 표시됩니다.|  
|제안 해결 방법|[FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported](https://msdn.microsoft.com/library/system.windows.frameworkcompatibilitypreferences.areinactiveselectionhighlightbrushkeyssupported\(v=vs.110\).aspx) 속성을 false로 설정하여 이전(.NET 4.0) 동작을 복원할 수 있습니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Windows.Controls.TextBox?displayProperty=fullName>|  
|분석기|CD0004|  
  
<a name="diagnostic5"></a>   
## <a name="5-listtforeach-can-throw-exception-when-modifying-list-item"></a>5: 목록\<T>.ForEach는 목록 항목을 수정할 때 예외를 throw할 수 있습니다  
  
|||  
|-|-|  
|설명|.NET 4.5부터는 호출 컬렉션의 요소가 수정되면 `List<T>.ForEach` 열거자가 InvalidOperationException 예외를 throw합니다. 이전에는 예외를 throw하지 않고 경합 상태가 발생할 수 있었습니다.|  
|제안 해결 방법|이상적으로, 안전한 작업을 위해 요소를 열거하는 동안 목록을 수정하지 않도록 코드를 수정해야 합니다. 그러나 이전 동작으로 되돌리려면 응용 프로그램이 .NET 4.0을 대상으로 할 수 있습니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|대상 변경|  
|영향을 받는 API|<xref:System.Collections.Generic.List%601.ForEach%28System.Action%7B%600%7D%29?displayProperty=fullName>|  
|분석기|CD0005|  
  
<a name="diagnostic6"></a>   
## <a name="6-systemuri-parsing-adheres-to-rfc-3987"></a>6: System.Uri 구문 분석이 RFC 3987을 준수  
  
|||  
|-|-|  
|세부 정보|.NET 4.5에서 URI 구문 분석은 여러 방법으로 변경되었습니다. 단, 이러한 변경 내용은 .NET 4.5를 대상으로 하는 코드에 영향을 줍니다. 이진 파일이 .NET 4.0을 대상으로 하는 경우, 이전 동작이 관찰됩니다. .NET 4.5의 URI 구문 분석 변경 내용은 다음을 포함합니다.<br /><br /> URI 구문 분석은 RFC 3987의 최신 규칙에 따라 정규화 및 문자 검사를 수행합니다<br /><br /> 유니코드 정규화 형식 C는 URI의 호스트 부분에서만 수행됩니다<br /><br /> 잘못된 mailto: URI가 예외를 발생시킵니다<br /><br /> 이제 패스 세그먼트 끝의 후행 점이 유지됩니다<br /><br /> `file://` URI는 `?` 문자를 이스케이프하지 않습니다<br /><br /> 유니코드 제어 문자 `U+0080`에서 `U+009F`는 지원되지 않습니다<br /><br /> 쉼표 문자 `,` 또는 `%2c`는 자동으로 이스케이프가 해제되지 않습니다|  
|제안 해결 방법|이전 .NET 4.0 URI 구문 분석 의미 체계가 필요한 경우(주로 필요하지 않음) .NET 4.0을 대상으로 하여 사용할 수 있습니다. 이것은 어셈블리에서 TargetFrameworkAttribute 속성을 사용하거나 ‘프로젝트 속성’ 페이지에서 Visual Studio의 프로젝트 시스템 UI 통해 수행할 수 있습니다.|  
|범위|주요함|  
|버전|4.5|  
|형식|대상 변경|  
|영향을 받는 API|<xref:System.Uri.%23ctor%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.Uri%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.String%2CSystem.UriKind%2CSystem.Uri%40%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.Uri%2CSystem.String%2CSystem.Uri%40%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.Uri%2CSystem.Uri%2CSystem.Uri%40%29?displayProperty=fullName>|  
|분석기|CD0006D<br /><br /> CD0006C<br /><br /> CD0006F<br /><br /> CD0006E<br /><br /> CD0006A<br /><br /> CD0006G<br /><br /> CD0006B|  
  
<a name="diagnostic10"></a>   
## <a name="10-systemuri-escaping-now-supports-rfc-3986-httptoolsietforghtmlrfc3986"></a>10: System.Uri 이스케이프가 RFC 3986(http://tools.ietf.org/html/rfc3986)을 지원  
  
|||  
|-|-|  
|세부 정보|.NET 4.5에서 URI 이스케이프가 [RFC 3986](http://tools.ietf.org/html/rfc3986)를 지원하도록 변경되었습니다. 특정 변경 내용은 다음을 포함합니다.<br /><br /> `EscapeDataString`은 RFC 3986을 기반으로 하는 예약된 문자를 이스케이프합니다.<br /><br /> `EscapeUriString`은 예약된 문자를 이스케이프하지 않습니다.<br /><br /> `UnescapeDataString`은 잘못된 이스케이프 시퀀스가 발생하는 경우 예외를 throw하지 않습니다.<br /><br /> 예약되지 않은 이스케이프된 문자는 이스케이프 해제됩니다.|  
|제안 해결 방법|잘못된 이스케이프 시퀀스의 경우 throw하여 응용 프로그램이 UnescapeDataString을 의존하지 않도록 업데이트합니다. 이제 이러한 시퀀스를 직접 발견해야 합니다.<br /><br /> 마찬가지로, 이스케이프되거나 이스케이프되지 않은 URI 및 데이터 문자열이 .NET 4.0과 .NET 4.5에서 달라질 수 있으며 .NET 버전 간에 직접 비교되지 않아야 합니다. 대신 어떤 비교도 실행되기 전에 단일 .NET 버전에 구문 분석되고 표준화되어야 합니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Uri.EscapeDataString%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.EscapeUriString%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.UnescapeDataString%28System.String%29?displayProperty=fullName>|  
|분석기|CD0010A<br /><br /> CD0010B<br /><br /> CD0010C|  
  
<a name="diagnostic11"></a>   
## <a name="11-systemnetpeertopeercollaboration-unavailable-on-windows-8"></a>11: Windows 8에서 System.Net.PeerToPeer.Collaboration을 사용할 수 없습니다  
  
|||  
|-|-|  
|세부 정보|System.Net.PeerToPeer.Collaboration 네임스페이스는 Windows 8 이상에서 사용할 수 없습니다.|  
|제안 해결 방법|Windows 8 이상을 지원하는 응용 프로그램은 이 네임스페이스 또는 해당 멤버에 종속되지 않도록 업데이트되어야 합니다.|  
|범위|주요함|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Net.PeerToPeer.Collaboration?displayProperty=fullName>|  
|분석기|CD0011|  
  
<a name="diagnostic12"></a>   
## <a name="12-mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a>12: MEF 카탈로그는 IEnumerable을 구현하므로 더 이상 직렬 변환기를 만드는 데 사용할 수 없습니다  
  
|||  
|-|-|  
|설명|.NET Framework 4.5부터 MEF 카탈로그는 IEnumerable을 구현하므로 더 이상 직렬 변환기(XmlSerializer 개체)를 만드는 데 사용할 수 없습니다. MEF 카탈로그를 serialize하려고 하면 예외가 throw됩니다.|  
|제안 해결 방법|직렬 변환기를 만드는데 MEF를 더 이상 사용할 수 없음|  
|범위|주요함|  
|버전|4.5|  
|형식|런타임|  
|분석기|CD0012|  
  
<a name="diagnostic13"></a>   
## <a name="13-missing-target-framework-moniker-results-in-40-behavior"></a>13: 누락된 대상 프레임워크 모니커로 4.0 동작 발생  
  
|||  
|-|-|  
|세부 정보|어셈블리 수준이 적용된 [TargetFrameworkAttribute](https://msdn.microsoft.com/library/system.runtime.versioning.targetframeworkattribute\(v=vs.110\).aspx)가 없는 응용 프로그램은 .NET Framework 4.0의 의미 체계(쿼크)를 사용하여 자동으로 실행합니다. 높은 품질을 보장하려면 모든 바이너리가 빌드될 때 사용된 .NET Framework의 버전을 나타내는 TargetFrameworkAttribute로 명시적으로 특성을 사용하는 것이 좋습니다. 프로젝트 파일에서 대상 프레임워크 모니커를 사용하면 MSBuild는 TargetFrameworkAttribute를 자동으로 적용합니다.|  
|제안 해결 방법|[대상 프레임워크 특성](https://msdn.microsoft.com/library/system.runtime.versioning.targetframeworkattribute\(v=vs.110\).aspx)은 어셈블리에 직접 특성을 추가하거나 [프로젝트 파일에서 대상 프레임워크를 지정하거나 또는 Visual Studio의 프로젝트 속성 GUI](http://blogs.msdn.com/b/visualstudio/archive/2010/05/19/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework.aspx)를 통해 제공되어야 합니다.|  
|범위|주요함|  
|버전|4.5|  
|형식|런타임|  
|분석기|CD0013|  
  
<a name="diagnostic14"></a>   
## <a name="14-no-longer-able-to-set-enableviewstatemac-to-false"></a>14: 더 이상 EnableViewStateMac를 false로 설정할 수 없음  
  
|||  
|-|-|  
|설명|ASP.NET에서 개발자는 더 이상 `<pages enableViewStateMac="false"/>` 또는 `<@Page EnableViewStateMac="false" %>`를 지정할 수 없습니다. 포함된 뷰 상태가 사용된 모든 요청에 뷰 상태 MAC(메시지 인증 코드)가 적용됩니다. EnableViewStateMac 속성이 false로 명시적으로 설정된 앱에만 영향을 줍니다.|  
|제안 해결 방법|EnableViewStateMac은 true로 간주되어야 하고 모든 결과 MAC 오류는 (MAC 오류 원인의 세부 정보에 따른 여러 해결 방법을 포함하는 [이](https://support.microsoft.com/kb/2915218) 참고 자료에 설명된 대로) 해결되어야 합니다.|  
|범위|주요함|  
|버전|4.5.2|  
|형식|런타임|  
|분석기|CD0014|  
  
<a name="diagnostic18"></a>   
## <a name="18-blockingcollectionttrytakefromany-does-not-throw-anymore"></a>18: BlockingCollection\<T>.TryTakeFromAny는 더 이상 throw하지 않습니다  
  
|||  
|-|-|  
|세부 정보|입력 컬렉션 중 하나가 완료됨으로 표시될 경우 `BlockingCollection<T>.TryTakeFromAny(BlockingCollection<T>[], T)`은 더이상 -1을 반환하지 않고 `BlockingCollection<T>.TakeFromAny`는 더 이상 예외를 throw하지 않습니다. 이러한 변경을 통해 컬렉션 중 하나가 비어 있거나 완료되었더라도 나머지 컬렉션에는 검색할 수 있는 항목이 아직 있는 경우 컬렉션을 사용할 수 있습니다.|  
|제안 해결 방법|차단 컬렉션 완료 시 제어 흐름 목적으로 -1을 반환하는 TryTakeFromAny 또는 throw하는 TakeFromAny가 사용된 경우, 이러한 코드는 `.Any(b => b.IsCompleted)`를 사용하도록 변경되어 해당 조건을 검색하도록 해야 합니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName><br /><br /> <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName><br /><br /> <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.Int32%29?displayProperty=fullName><br /><br /> <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.TimeSpan%29?displayProperty=fullName>|  
|분석기|CD0018A<br /><br /> CD0018B|  
  
<a name="diagnostic19"></a>   
## <a name="19-xmlschemaexception-now-sets-line-positions-properly"></a>19: XmlSchemaException이 줄 위치를 제대로 설정  
  
|||  
|-|-|  
|설명|LoadOptions.SetLineInfo 값이 Load 메서드에 전달되고 유효성 검사 오류가 발생하는 경우 XmlSchemaException.LineNumber 및 XmlSchemaException.LinePosition 속성이 줄 정보를 포함합니다.|  
|제안 해결 방법|XmlSchemaException.LineNumber 및 XmlSchemaException.LinePosition 설정되지 않는 것을 가정하는 예외 처리 코드는 업데이트해야 합니다. 이러한 속성은 XML을 로드하는 동안 SetLineInfo를 사용할 때 제대로 설정되지 않기 때문입니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Xml.Linq.LoadOptions?displayProperty=fullName>|  
|분석기|CD0019|  
  
<a name="diagnostic20"></a>   
## <a name="20-systemactivities-is-now-aptca"></a>20: System.Activities는 APTCA로 됩니다  
  
|||  
|-|-|  
|세부 정보|어셈블리가 AllowPartiallyTrustedCallersAttribute 특성으로 표시됩니다.|  
|제안 해결 방법|파생 클래스는 SecurityCriticalAttribute로 표시할 수 없습니다. 이전에는 파생된 형식을 SecurityCriticalAttribute로 표시해야 했습니다. 그러나 이 변경은 실제로 영향을 주어서는 안 됩니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|분석기|CD0020|  
  
<a name="diagnostic21"></a>   
## <a name="21-workflow-30-types-are-obsolete"></a>21: 워크플로 3.0 형식은 사용되지 않음  
  
|||  
|-|-|  
|세부 정보|System.Workflow 네임스페이스의 Windows Workflow Foundation(WWF) 3.0 API는 이제 사용되지 않습니다.|  
|제안 해결 방법|System.Activities 새 WWF 4.0 API를 대신 사용해야 합니다. 새 API를 사용하는 예제는 [여기](https://msdn.microsoft.com/library/jj205427.aspx)에서 찾을 수 있으며 추가 참고 자료은 [여기](http://blogs.msdn.com/b/workflowteam/archive/2012/02/08/deprecatingwf3.aspx)에서 볼 수 있습니다. 또는 WWF 3.0 API가 계속 지원되므로 사용할 수 있으며, 빌드 시간 경고는 표시되지 않거나 이전 컴파일러를 사용하여 방지할 수 있습니다.|  
|범위|주요함|  
|버전|4.5|  
|형식|대상 변경|  
|분석기|CD0021|  
  
<a name="diagnostic22"></a>   
## <a name="22-some-workflow-drag-and-drop-apis-are-obsolete"></a>22: 일부 워크플로 끌어서 놓기 API가 사용되지 않음  
  
|||  
|-|-|  
|세부 정보|워크플로 끌어서 놓기 API는 사용되지 않으며 응용 프로그램이 4.5에 대해 다시 빌드하는 경우 컴파일러 경고가 발생합니다.|  
|제안 해결 방법|여러 개체에 대한 작업을 지원하는 새 [DragDropHelper](https://msdn.microsoft.com/library/system.activities.presentation.dragdrophelper\(v=vs.110\).aspx) API를 대신 사용해야 합니다. 또는 빌드 경고를 표시하지 않거나 이전 컴파일러를 사용하여 방지할 수 있습니다. API는 계속 지원됩니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|대상 변경|  
|영향을 받는 API|<xref:System.Activities.Presentation.DragDropHelper.DoDragMove%28System.Activities.Presentation.WorkflowViewElement%2CSystem.Windows.Point%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView%28System.Windows.DragEventArgs%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem%28System.Windows.DragEventArgs%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject%28System.Windows.DependencyObject%2CSystem.Windows.DragEventArgs%2CSystem.Activities.Presentation.EditingContext%29?displayProperty=fullName>|  
|분석기|CD0022|  
  
<a name="diagnostic23"></a>   
## <a name="23-new-ambiguous-dispatcherinvoke-overloads-could-result-in-different-behavior"></a>23: (모호한) 새 Dispatcher.Invoke 오버로드는 다른 동작을 발생시킬 있습니다  
  
|||  
|-|-|  
|설명|.NET Framework 4.5는 Dispatcher.Invoke에 System.Action 형식의 매개 변수를 포함하는 새 오버로드를 추가합니다. 기존 코드를 다시 컴파일하면 컴파일러는 Delegate 매개 변수를 가진 Dispatcher.Invoke 메서드에 대한 호출로서 System.Action 매개 변수를 갖는 Dispatcher.Invoke 메서드에 대한 호출을 해결할 수 있습니다. Delegate 매개 변수를 가진 Dispatcher.Invoke 오버로드를 호출함으로써 해결된 System.Action 매개 변수를 가진 Dispatcher.Invoke 오버로드를 호출하는 경우, 다음과 같은 동작 차이가 발생할 수 있습니다.<br /><br /> 예외가 발생하는 경우 Dispatcher.UnhandledExceptionFilter 및 Dispatcher.UnhandledException 이벤트가 발생하지 않습니다. 대신, 예외는 UnobservedTaskException 이벤트에 의해 처리됩니다.<br /><br /> DispatcherOperation.Result와 같은 일부 멤버에 대한 호출은 작업이 완료될 때까지 차단됩니다.|  
|제안 해결 방법|모호성 (및 예외를 처리하거나 동작을 차단하는 잠재적인 문제)을 방지하려면 Dispatcher.Invoke를 호출하는 코드가 빈 개체를 두 번째 매개 변수로 Invoke 호출에 전달하여 .NET 4.0 메서드 오버로드를 확인하도록 할 수 있습니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|대상 변경|  
|영향을 받는 API|<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.TimeSpan%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.TimeSpan%2CSystem.Windows.Threading.DispatcherPriority%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.Windows.Threading.DispatcherPriority%2CSystem.Object%5B%5D%29?displayProperty=fullName>|  
|분석기|CD0023|  
  
<a name="diagnostic24"></a>   
## <a name="24-encoderparameter-ctor-is-obsolete"></a>24: EncoderParameter ctor가 사용되지 않음  
  
|||  
|-|-|  
|세부 정보|`EncoderParameter.EncoderParameter(Encoder, Int32, Int32, Int32)` 생성자는 이제 사용되지 않으며 사용하는 경우 빌드 경고가 발생합니다.|  
|제안 해결 방법|`EncoderParameter.EncoderParameter(Encoder, Int32, Int32, Int32)` 생성자가 계속 작동하지만 .NET 4.5 도구를 사용하여 코드를 다시 컴파일할 때 사용되지 않는 빌드 경고를 방지하려면 다음 생성자를 대신 사용해야 합니다. [EncoderParameter.EncoderParameter(Encoder, Int32, EncoderParameterValueType, IntPtr)](https://msdn.microsoft.com/library/hh875096\(v=vs.110\).aspx).|  
|범위|사소함|  
|버전|4.5|  
|형식|대상 변경|  
|영향을 받는 API|<xref:System.Drawing.Imaging.EncoderParameter.%23ctor%28System.Drawing.Imaging.Encoder%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|분석기|CD0024|  
  
<a name="diagnostic26"></a>   
## <a name="26-change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a>26: 제한 시간 인수가 있는 Task.WaitAll 메서드에 대한 동작 변경  
  
|||  
|-|-|  
|세부 정보|.NET 4.5에서 Task.WaitAll 동작이 보다 일관성 있게 되었습니다.<br /><br /> .NET Framework 4에서는 이러한 메서드가 일관되지 않게 동작했었습니다. 제한 시간이 만료되고 메서드 호출 전에 하나 이상의 작업이 완료되거나 취소되면 이 메서드는 AggregateException 예외를 throw합니다. 제한 시간이 만료되고 메서드 호출 전에 완료되거나 취소된 작업은 없지만 메서드 호출 후에 하나 이상의 작업이 완료되거나 취소되면 이 메서드는 false를 반환합니다.<br />.NET Framework 4.5에서, 시간 제한 간격이 만료될 때 모든 작업이 아직 실행되고 있는 경우 이러한 메서드 오버로드에서 이제 false를 반환하고, 입력 작업이 취소되고(메서드 호출 전후 여부와 상관없이) 다른 작업이 실행되고 있지 않은 경우에만 AggregateException 예외를 throw합니다.|  
|제안 해결 방법|.NET 4.6은 대기된 모든 작업이 시간 제한 전에 완료되어야 throw하기 때문에 WaitAll이 호출되기 전에 취소된 작업을 탐지하는 방법으로 AggregateException이 catch된 경우 해당 코드는 대신 IsCanceled 속성(예: .Any(t => t.IsCanceled))을 통해 동일한 탐지를 해야 합니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.Int32%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.Int32%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.TimeSpan%29?displayProperty=fullName>|  
|분석기|CD0026|  
  
<a name="diagnostic27"></a>   
## <a name="27-change-in-behavior-in-data-definition-language-ddl-apis"></a>27: DDL(데이터 정의 언어) API에서 동작 변경  
  
|||  
|-|-|  
|설명|AttachDBFilename이 지정되면 DDL API의 동작은 다음과 같이 변경됩니다.<br /><br /> 연결 문자열에 초기 카탈로그 값을 지정할 필요는 없습니다. 이전에는 AttatchDBFilename 및 초기 카탈로그가 모두 필요했습니다.<br /><br /> AttatchDBFilename 및 초기 카탈로그가 모두 지정되고 제공된 MDF 파일이 있는 경우 ObjectContext.DatabaseExists 메서드는 true를 반환합니다. 이전에는 false를 반환했습니다.<br /><br /> AttatchDBFilename 및 초기 카탈로그가 모두 지정되고 제공된 MDF 파일이 있는 경우 ObjectContext.DatabaseExists 메서드 호출은 파일을 삭제합니다.<br /><br /> 연결 문자열이 존재하지 않는 MDF와 존재하지 않는 카탈로그를 사용하여 AttachDBFilename 값을 지정할 때 ObjectContext.DeleteDatabase가 호출되면 메서드가 InvalidOperationException 예외를 throw합니다. 이전에는 SqlException 예외를 throw했습니다.|  
|제안 해결 방법|이러한 변경으로 인해 DDL API를 사용하는 도구와 응용 프로그램을 보다 쉽게 빌드할 수 있습니다. 이러한 변경 사항은 다음 시나리오에서 응용 프로그램 호환성에 영향을 줄 수 있습니다.<br /><br /> 사용자는 ObjectContext.DatabaseExists가 true를 반환하는 경우 ObjectContext.DeleteDatabase를 호출하는 대신 직접 DROP DATABASE 명령을 실행하는 코드를 씁니다. 이는 데이터베이스가 연결되지 않았지만 MDF 파일이 있는 경우 기존 코드를 중단시킵니다.<br /><br /> 사용자는 초기 카탈로그 및 MDF 파일이 없을 때 InvalidOperationException 예외보다는 SqlException 예외를 throw하기 위해 ObjectContext.DeleteDatabase 메서드를 기대하는 코드를 씁니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|분석기|CD0027|  
  
<a name="diagnostic28"></a>   
## <a name="28-machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a>28: MachineKey.Encode 및 MachineKey.Decode 메서드는 사용되지 않습니다  
  
|||  
|-|-|  
|세부 정보|이러한 메서드는 이제 사용되지 않습니다. 이러한 메서드를 호출하는 코드를 컴파일하면 컴파일러 경고가 생성됩니다.|  
|제안 해결 방법|권장되는 대안은 [MachineKey.Protect](https://msdn.microsoft.com/library/system.web.security.machinekey.protect\(v=vs.110\).aspx) 및 [MachineKey.Unprotect](https://msdn.microsoft.com/library/system.web.security.machinekey.unprotect\(v=vs.110\).aspx)입니다. 또는 빌드 경고를 표시하지 않거나 이전 컴파일러를 사용하여 방지할 수 있습니다. API는 계속 지원됩니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|대상 변경|  
|영향을 받는 API|<xref:System.Web.Security.MachineKey.Decode%28System.String%2CSystem.Web.Security.MachineKeyProtection%29?displayProperty=fullName><br /><br /> <xref:System.Web.Security.MachineKey.Encode%28System.Byte%5B%5D%2CSystem.Web.Security.MachineKeyProtection%29?displayProperty=fullName>|  
|분석기|CD0028|  
  
<a name="diagnostic29"></a>   
## <a name="29-the-replace-method-in-odata-urls-is-disabled-by-default"></a>29: OData URL의 Replace 메서드는 기본적으로 비활성화되어 있음  
  
|||  
|-|-|  
|설명|.NET Framework 4.5를 시작할 때 OData URL의 Replace 메서드는 기본적으로 비활성화되어 있습니다. OData Replace가 비활성화되면(기본값) Replace 기능(일반적이지 않음)을 포함한 모든 사용자 요청이 실패합니다.|  
|제안 해결 방법|Replace 메서드가 필요한 경우(일반적이지 않음) [구성 설정](https://msdn.microsoft.com/library/system.data.services.configuration.dataservicesfeaturessection.replacefunction.aspx)을 통해 다시 사용할 수 있습니다. 그러나 활성화된 Replace 메서드는 보안 취약점을 열 수 있어 신중하게 검토한 후에 사용해야 합니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Data.Services.DataService%601?displayProperty=fullName>|  
|분석기|CD0029|  
  
<a name="diagnostic30"></a>   
## <a name="30-systemservicemodelwebwebservicehost-object-no-longer-adds-a-default-endpoint"></a>30: System.ServiceModel.Web.WebServiceHost 개체는 더 이상 기본 끝점을 추가하지 않습니다  
  
|||  
|-|-|  
|세부 정보|System.ServiceModel.Web.WebServiceHost 개체는 명시적 끝점이 응용 프로그램 코드에 의해 추가될 경우 더 이상 기본 끝점을 추가하지 않습니다.|  
|제안 해결 방법|사용자가 기본 끝점에 연결할 수 있게 되기를 예상하고 다른 명시적 끝점이 WebServiceHost에 추가되어 있는 경우 기본 끝점도 명시적으로 추가되어야 합니다(AddDefaultEndpoints 사용).|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.ServiceModel.Description.ServiceEndpoint%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%2CSystem.Uri%29?displayProperty=fullName>|  
|분석기|CD0030A<br /><br /> CD0030B|  
  
<a name="diagnostic31"></a>   
## <a name="31-eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a>31: EventSource.WriteEvent impls는 수신된 매개 변수와 동일한 WhiteEvent를 전달해야 합니다(추가 ID).  
  
|||  
|-|-|  
|세부 정보|이제 런타임에서는 다음을 지정하는 계약이 적용됩니다. ETW 이벤트 메서드를 정의하는 EventSource에서 파생된 클래스는 이벤트 ID 다음에 ETW 이벤트 메서드가 전달된 동일한 인수를 사용하여 기본 클래스 EventSource.WriteEvent 메서드를 호출해야 합니다.|  
|제안 해결 방법|EventListener가 이 계약을 위반하는 이벤트 소스에 대한 프로세스에서 EventSource 데이터를 읽는 경우 IndexOutOfRangeException 예외가 throw됩니다.|  
|범위|사소함|  
|버전|4.5.1|  
|형식|런타임|  
|분석기|CD0031|  
  
<a name="diagnostic32"></a>   
## <a name="32-minfreememorypercentagetoactiveservice-is-now-respected"></a>32: MinFreeMemoryPercentageToActiveService가 적용됩니다  
  
|||  
|-|-|  
|세부 정보|이 설정은 WCF 서비스 활성화를 위해 서버에서 사용할 수 있는 최소 메모리를 지정합니다. OutOfMemoryException 예외를 방지하기 위해 설계되었습니다. .NET Framework 4.5에서 이 설정은 영향을 주지 않았습니다. .NET Framework 4.5.1에서 해당 설정이 적용됩니다.|  
|제안 해결 방법|웹 서버의 사용 가능한 메모리가 구성 설정에서 정의된 백분율보다 적은 경우 예외가 발생합니다. 성공적으로 시작되었지만 제한된 메모리 환경에서 실행되는 일부 WCF 서비스의 경우 실패할 수 있습니다.|  
|범위|사소함|  
|버전|4.5.1|  
|형식|런타임|  
|분석기|CD0032|  
  
<a name="diagnostic33"></a>   
## <a name="33-xmltextreader-dtd-entity-expansion-is-limited-to-10000000-characters"></a>33: XmlTextReader DTD 엔터티 확장은 10,000,000자로 제한됨  
  
|||  
|-|-|  
|세부 정보|이제 DTD 엔터티 확장은 10,000,000자로 제한됩니다. DTD 엔터티 확장 없이 또는 제한된 DTD 엔터티 확장으로 XML 파일을 로드해도 영향을 받지 않습니다. 이제 파일에 10,000,000자를 초과하는 문자로 확장되는 DTD 엔터티가 있으면 로드하지 못하고 예외를 throw합니다.|  
|제안 해결 방법|DTD 엔터티 확장의 제한이 너무 낮은 경우 10,000,000 값은 [XmlReaderSettings.MaxCharactersFromEntities](https://msdn.microsoft.com/library/system.xml.xmlreadersettings.maxcharactersfromentities%28v=vs.110%29.aspx) 속성으로 재정의됩니다. 적절한 MaxCharactersFromEntity 값의 XmlReaderSettings는 [XmlReader.Create](https://msdn.microsoft.com/library/System.Xml.XmlReader.Create\(v=vs.110\).aspx)로 전달될 수 있습니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Xml.XmlTextReader.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%2CSystem.Xml.XmlNodeType%2CSystem.Xml.XmlParserContext%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.TextReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.TextReader%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.Stream%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.TextReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.TextReader%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.Xml.XmlNodeType%2CSystem.Xml.XmlParserContext%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader?displayProperty=fullName>|  
|분석기|CD0033|  
  
<a name="diagnostic35"></a>   
## <a name="35-xslt-style-sheet-exception-message-changed"></a>35: XSLT 스타일 시트 예외 메시지가 변경됨  
  
|||  
|-|-|  
|설명|.NET Framework 4.5에서 XSLT 파일이 너무 복잡할 경우 오류 메시지의 텍스트는 "스타일시트가 너무 복잡합니다."입니다. 이전 버전에서 오류 메시지는 "XSLT 컴파일 오류입니다."였습니다. 오류 메시지 텍스트에 종속되어 있는 응용 프로그램 코드는 더 이상 작동하지 않습니다. 그러나 예외 형식은 동일하게 유지되므로 이 변경은 실제 영향을 미쳐서는 안 됩니다.|  
|제안 해결 방법|이 오류 조건에서 새 메시지를 예상하여 예외 메시지에 따라 응용 프로그램 코드를 업데이트하거나 더욱 좋은 방법은 변경되지 않는 예외 형식([XsltException](https://msdn.microsoft.com/library/system.xml.xsl.xsltexception\(v=vs.110\).aspx))만 의존하도록 코드를 업데이트합니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Reflection.MethodInfo%2CSystem.Byte%5B%5D%2CSystem.Type%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.String%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XPath.IXPathNavigable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XPath.IXPathNavigable%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XmlReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XmlReader%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName>|  
|분석기|CD0035|  
  
<a name="diagnostic36"></a>   
## <a name="36-wf-serializes-expressionsliteralt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>36: WF가 Expressions.Literal\<T> DateTimes를 직렬화합니다(사용자 지정 XAML 파서 중단)  
  
|||  
|-|-|  
|설명|연결된 [ValueSerializer](https://msdn.microsoft.com/library/system.windows.markup.valueserializer\(v=vs.110\).aspx) 개체는 Second 및 Millisecond 구성 요소 값이 0이 아니고 (DateTime 값에 대해) DateTime.Kind 속성이 문자열 대신 속성 요소 구문에 지정되지 않은 DateTime 또는 DateTimeOffset 개체를 변환합니다. 이 변경은 DateTime 및 DateTimeOffset 값이 라운드트립되는 것을 허용합니다. 입력 XAML이 특성 구문에 있다고 가정하는 사용자 지정 XAML 파서가 올바르게 작동하지 않습니다.|  
|제안 해결 방법|이 변경은 DateTime 및 DateTimeOffset 값이 라운드트립되는 것을 허용합니다. 입력 XAML이 특성 구문에 있다고 가정하는 사용자 지정 XAML 파서가 올바르게 작동하지 않습니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|분석기|CD0036|  
  
<a name="diagnostic37"></a>   
## <a name="37-new-enum-values-in-wpfs-pagerangeselection"></a>37: WPF의 PageRangeSelection에 새 열거형 값  
  
|||  
|-|-|  
|세부 정보|[PageRangeSelection](https://msdn.microsoft.com/library/system.windows.controls.pagerangeselection\(v=vs.110\).aspx) 열거형에 새로운 두 멤버(CurrentPage 및 SelectedPage)가 추가되었습니다.|  
|제안 해결 방법|대부분의 경우 이러한 변경은 사용자 코드에 영향을 주지 않습니다. 다만 PageRangeSelection 형식의 Enum.GetNames 또는 Enum.GetValues 호출에 존재하는 요소의 특정 수에 종속된 코드는 수정되어야 합니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>|  
|분석기|CD0037|  
  
<a name="diagnostic38"></a>   
## <a name="38-wpf-dispatchersynchronizationcontextcreatecopy-now-returns-a-new-copy-instead-of-the-current-instance"></a>38: 이제 WPF DispatcherSynchronizationContext.CreateCopy는 현재 인스턴스 대신 새 복사본을 반환  
  
|||  
|-|-|  
|설명|.NET Framework 4에서 DispatcherSynchronizationContext.CreateCopy()는 주로 성능 최적화로서 현재 인스턴스로 참조를 반환합니다. .NET Framework 4.5에서는 처음으로 동일한 참조가 실행 스레드를 올바른 동기화 컨텍스트에 나타내도록 마무리하는 것을 가능하게 하는 새 인스턴스를 반환합니다.  이러한 참조의 ID를 확인하는 코드가 영향을 받기는 어렵지만, 변경 내용 때문에 DispatcherSynchronizationContext.CreateCopy를 호출하는 코드는 .NET Framework 4.5 이상으로의 마이그레이션 일부로 테스트되어야 합니다.|  
|제안 해결 방법|DispatcherSynchronizationContext.CreateCopy()는 이제 새로운 SynchronizationContext 개체를 반환한다는 사실을 기억하십시오.  이전에는 이러한 방식으로 생성된 참조의 동등성을 사용한 코드는 적절한 컨텍스트에 있는지 실제로 확인되지 않았지만 .NET 4.5 이상에 대해 빌드할 때는 확인됩니다.  문제가 발생할 가능성은 작지만 발생하는 경우 영향을 받은 코드 경로를 실행하는 것으로 확인하기에 충분할 것입니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=fullName>|  
|분석기|CD0038|  
  
<a name="diagnostic39"></a>   
## <a name="39-systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a>39: 개체를 삭제한 후 System.Threading.Tasks.Task는 더 이상 ObjectDisposedException을 throw하지 않습니다  
  
|||  
|-|-|  
|설명|Task.IAsyncResult.AsyncWaitHandle을 제외하고 System.Threading.Tasks.Task 메서드는 개체가 삭제된 후에 더 이상 ObjectDisposedException 예외를 throw하지 않습니다.<br />이 변경은 캐시된 작업의 사용을 지원합니다. 예를 들어, 메서드는 새로운 작업을 할당하는 대신에 이미 완료된 작업을 나타내기 위해 캐시된 작업을 반환할 수 있습니다. 작업의 모든 소비자는 다시 사용할 수 없게 렌더링된 작업을 삭제할 수 있었기 때문에 이전 .NET Framework 버전에서는 이것이 불가능했습니다.|  
|제안 해결 방법|작업 메서드는 개체가 삭제되는 경우에 ObjectDisposedExceptions를 더 이상 throw하지 않는다는 것을 기억하십시오. 응용 프로그램이 작업이 삭제되었는지 알도록 이 예외에 종속된 경우 [Task.Status](https://msdn.microsoft.com/library/system.threading.tasks.task.status\(v=vs.110\).aspx)를 사용하여 작업의 상태를 명시적으로 확인하도록 업데이트해야 합니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|분석기|CD0039|  
  
<a name="diagnostic40"></a>   
## <a name="40-different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a>40: ObjectContext.CreateDatabase 및 DbProviderServices.CreateDatabase 메서드를 처리하는 다른 예외  
  
|||  
|-|-|  
|설명|.NET 4.5부터 데이터베이스 만들기에 실패하면 `CreateDatabase` 메서드는 빈 데이터베이스를 삭제하려고 합니다. 해당 작업에 성공하면 원래의 `SQLException`이 전파됩니다(항상 .NET 4.0에서 throw된 `InvalidOperationException` 대신).|  
|제안 해결 방법|ObjectContext.CreateDatabase 또는 DbProviderServices.CreateDatabase를 실행하는 동안 InvalidOperationException를 포착할 때 SQLExceptions도 발견됩니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Data.Common.DbProviderServices.CreateDatabase%28System.Data.Common.DbConnection%2CSystem.Nullable%7BSystem.Int32%7D%2CSystem.Data.Metadata.Edm.StoreItemCollection%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName>|  
|분석기|CD0040|  
  
<a name="diagnostic41"></a>   
## <a name="41-objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a>41: 이제 ObjectContext.Translate와 ObjectContext.ExecuteStoreQuery가 열거형 형식을 지원함  
  
|||  
|-|-|  
|세부 정보|.NET 4.0에서는 `ObjectContext.Translate` 및 `ObjectContext.ExecuteStoreQuery` 메서드의 제네릭 매개 변수 `T`가 열거형일 수 없었습니다. 이제 이 시나리오가 지원됩니다.|  
|제안 해결 방법|.NET 4.0의 열거형 형식에서 좌표 이동 또는 ExecuteStoreQuery가 호출되면 ‘0’이 반환되었습니다. 해당 동작이 필요한 경우 호출은 상수 0(또는 열거형 해당 항목)으로 대체되어야 합니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601%28System.String%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601%28System.String%2CSystem.String%2CSystem.Data.Objects.MergeOption%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.Translate%60%601%28System.Data.Common.DbDataReader%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.Translate%60%601%28System.Data.Common.DbDataReader%2CSystem.String%2CSystem.Data.Objects.MergeOption%29?displayProperty=fullName>|  
|분석기|CD0041|  
  
<a name="diagnostic42"></a>   
## <a name="42-enumerableemptytresult-always-returns-cached-instance"></a>42: Enumerable.Empty\<TResult>가 항상 캐시된 인스턴스를 반환  
  
|||  
|-|-|  
|세부 정보|.NET 4.5부터 `Enumerable.Empty`는 항상 캐시된 내부 인스턴스 `IEnumerable<T>`을 반환합니다.<br /><br /> 이전에 `Enumerable.Empty`는 API를 호출할 때 빈 `IEnumerable<T>`을 캐시했으며, 이 말은 즉 `Enumerable.Empty`가 빠르게 동시에 호출된 일부 조건에서 다른 형식의 인스턴스가 다른 호출에 대해 API로 반환되었다는 것입니다.|  
|제안 해결 방법|이전 동작이 명확하지 않았으므로 코드가 종속될 가능성이 작습니다. 그러나 빈 열거형은 비교되고 때로는 같지 않은 것으로 예상되는 드문 경우에는, `Enumerable.Empty`를 사용하는 대신 명시적인 빈 배열을 만들어야 합니다(`new T[0]`).|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Linq.Enumerable.Empty%60%601?displayProperty=fullName>|  
|분석기|CD0042|  
  
<a name="diagnostic43"></a>   
## <a name="43-httprequestcontentencoding-property-prohibits-utf7"></a>43: HttpRequest.ContentEncoding 속성이 UTF7를 금지  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.5부터 HttpRequests의 본문에 UTF-7 인코딩이 금지됩니다. 경우에 따라 UTF-7 수신 데이터에 종속되는 응용 프로그램 데이터가 제대로 디코딩되지 않습니다.|  
|제안 해결 방법|이상적으로 HttpRequests에서 인코딩 UTF-7을 사용하지 않도록 응용 프로그램을 업데이트해야 합니다. 대신에 [appSettings](https://msdn.microsoft.com/library/hh975440\(v=vs.110\).aspx) 요소의 `aspnet:AllowUtf7RequestContentEncoding` 특성을 사용하여 레거시 동작을 복원할 수 있습니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Web.HttpRequest.ContentEncoding?displayProperty=fullName>|  
|분석기|CD0043|  
  
<a name="diagnostic44"></a>   
## <a name="44-httputilityjavascriptstringencode-escapes-ampersand"></a>44: HttpUtility.JavaScriptStringEncode는 앰퍼샌드를 이스케이프  
  
|||  
|-|-|  
|설명|.NET Framework 4.5부터 JavaScriptStringEncode가 앰퍼샌드(&) 문자를 이스케이프합니다.|  
|제안 해결 방법|응용 프로그램이 이 메서드의 이전 동작에 종속되는 경우 aspnet:JavaScriptDoNotEncodeAmpersand 설정을 구성 파일에 있는 [ASP.NET appSettings 요소](https://msdn.microsoft.com/library/hh975440\(v=vs.110\).aspx)에 추가할 수 있습니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Web.HttpUtility.JavaScriptStringEncode%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Web.HttpUtility.JavaScriptStringEncode%28System.String%2CSystem.Boolean%29?displayProperty=fullName>|  
|분석기|CD0044A<br /><br /> CD0044B|  
  
<a name="diagnostic46"></a>   
## <a name="46-eventlistener-truncates-strings-with-embedded-nulls"></a>46: EventListener는 포함된 null이 있는 문자열을 자릅니다  
  
|||  
|-|-|  
|설명|EventListener는 포함된 null이 있는 문자열을 자릅니다. Null 문자는 EventSource 클래스에서 지원되지 않습니다. 이 변경 내용은 EventListene를 사용하여 프로세스의 EventSource 데이터를 읽고 null 문자를 구분 기호로 사용하는 앱에만 영향을 줍니다.|  
|제안 해결 방법|가능하면 포함된 null 문자를 사용하지 않도록 EventSource 데이터를 업데이트해야 합니다.|  
|범위|Microsoft Edge|  
|버전|4.5.1|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Diagnostics.Tracing.EventListener.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%2CSystem.Diagnostics.Tracing.EventKeywords%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%2CSystem.Diagnostics.Tracing.EventKeywords%2CSystem.Collections.Generic.IDictionary%7BSystem.String%2CSystem.String%7D%29?displayProperty=fullName>|  
|분석기|CD0046|  
  
<a name="diagnostic48"></a>   
## <a name="48-obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>48: ObsoleteAttribute가 WinMD 시나리오에서 ObsoleteAttribute와 DeprecatedAttribute를 내보냅니다  
  
|||  
|-|-|  
|세부 정보|Windows 메타데이터 라이브러리(.winmd 파일)를 만들 때 ObsoleteAttribute 특성은 ObsoleteAttribute 및 Windows.Foundation.DeprecatedAttribute 둘 다로 내보내집니다.|  
|제안 해결 방법|ObsoleteAttribute 특성이 사용된 기존 소스 코드를 다시 컴파일하면 C++/CX 또는 JavaScript의 해당 코드가 사용될 때 경고가 발생할 수 있습니다.<br /><br /> 관리 어셈블리의 코드에 ObsoleteAttribute 및 Windows.Foundation.DeprecatedAttribute를 둘 다 적용하지 않는 것이 좋습니다. 그럴 경우 빌드 경고가 발생할 수 있습니다.|  
|범위|Microsoft Edge|  
|버전|4.5.1|  
|형식|대상 변경|  
|분석기|CD0048A<br /><br /> CD0048B|  
  
<a name="diagnostic49"></a>   
## <a name="49-resolveassemblyreference-task-now-warns-on-dependencies-with-the-wrong-architecture"></a>49: ResolveAssemblyReference 작업이 잘못된 아키텍처를 사용하는 종속성에 경고  
  
|||  
|-|-|  
|세부 정보|이 작업은 참조 또는 해당 종속성이 앱 아키텍처와 일치하지 않음을 나타내는 경고 MSB3270을 내보냅니다. 예를 들어 anycpu 옵션으로 컴파일된 앱에 x86 참조가 포함된 경우 이 경고가 발생합니다. 이로 인해 앱의 런타임 오류가 발생할 수 있습니다(앱이 x64 프로세스로 배포된 경우).|  
|제안 해결 방법|영향에는 다음 두 가지 영역이 있습니다.<br /><br /> 다시 컴파일하면 앱이 이전 MSBuild 버전에서 컴파일되었을 때는 나타나지 않았던 경고가 생성됩니다. 하지만 런타임 오류가 발생한 소스를 경고에서 확인할 수 있으므로 이 문제를 조사하여 해결할 수 있습니다.<br /><br /> 경고가 오류로 처리되면 앱을 컴파일할 수 없습니다.|  
|범위|사소함|  
|버전|4.5.1|  
|형식|대상 변경|  
|분석기|CD0049|  
  
<a name="diagnostic51"></a>   
## <a name="51-wpf-textbox-defaults-to-undo-limit-of-100"></a>51: WPF TextBox 기본값이 100개의 제한을 실행 취소  
  
|||  
|-|-|  
|세부 정보|.NET 4.5에서는 WPF TextBox에 대한 실행 취소 제한 기본값은 100(.NET 4.0에서 무제한이던 것과 반대)|  
|제안 해결 방법|100개의 제한이 너무 낮으면 TextBox의 UndoLimit 속성으로 제한을 명시적으로 설정할 수 있습니다|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Windows.Controls.TextBox?displayProperty=fullName>|  
|분석기|CD0051|  
  
<a name="diagnostic55"></a>   
## <a name="55-exceptions-during-unobserved-processing-in-systemthreadingtaskstask-no-longer-propagate-on-finalizer-thread"></a>55: System.Threading.Tasks.Task의 관찰되지 않은 프로세스를 처리하는 동안 예외는 더 이상 종료자 스레드를 전파하지 않습니다  
  
|||  
|-|-|  
|세부 정보|System.Threading.Tasks.Task 클래스는 비동기 작업을 나타내기 때문에 비동기 처리를 하는 동안 발생하는 심각하지 않은 예외를 모두 catch합니다. .NET Framework 4.5에서는 예외가 관찰되지 않고 코드가 작업에서 대기하지 않으면 예외는 더 이상 종료자 스레드에서 전파되지 않고 가비지 수집 도중 프로세스와 충돌합니다. 이러한 변경으로 인해 관찰되지 않은 비동기 처리를 수행하기 위해 Task 클래스를 사용하는 응용 프로그램의 안정성이 향상됩니다.|  
|제안 해결 방법|응용 프로그램이 종료자 스레드를 전파하는 관찰되지 않은 비동기 예외에 종속되는 경우 이전의 동작은 [TaskScheduler.UnobservedTaskException](https://msdn.microsoft.com/library/system.threading.tasks.taskscheduler.unobservedtaskexception\(v=vs.110\).aspx) 이벤트에 대한 적절한 처리자를 제공하거나 [런타임 구성 요소](https://msdn.microsoft.com/library/jj160346%28v=vs.110%29.aspx)를 설정하여 복원할 수 있습니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Threading.Tasks.Task.Run%28System.Action%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Action%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%60%600%7D%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%60%600%7D%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7B%60%600%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7B%60%600%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Start?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Start%28System.Threading.Tasks.TaskScheduler%29?displayProperty=fullName>|  
|분석기|CD0055|  
  
<a name="diagnostic58"></a>   
## <a name="58-iasyncresultcompletedsynchronously-property-must-be-correct-for-the-resulting-task-to-complete"></a>58: 결과 작업을 완료하려면 IAsyncResult.CompletedSynchronously 속성이 정확해야 합니다  
  
|||  
|-|-|  
|세부 정보|TaskFactory.FromAsync를 호출할 때 IAsyncResult.CompletedSynchronously 속성이 올바르게 구현되어야 결과 작업을 완료할 수 있습니다. 즉, 이 속성은 구현이 동기적으로 완료된 경우에만 true를 반환해야 합니다. 이전에는 이 속성이 선택되어 있지 않았습니다.|  
|제안 해결 방법|IAsyncResult 구현이 작업이 동기적으로 완료된 경우에만 CompletedSynchronusly 속성에 대해 true를 반환한다면, 중단이 관찰되지 않습니다. 사용자는 소유하고 있는 IAsyncResult 구현(소유한 경우)을 검토하여 작업의 동기적 완료 여부를 올바르게 평가하는지 확인해야 합니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|대상 변경|  
|영향을 받는 API|<xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Threading.Tasks.TaskCreationOptions%2CSystem.Threading.Tasks.TaskScheduler%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Threading.Tasks.TaskCreationOptions%2CSystem.Threading.Tasks.TaskScheduler%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%601%7D%2C%60%600%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%601%7D%2C%60%600%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%602%7D%2C%60%600%2C%60%601%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%602%7D%2C%60%600%2C%60%601%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%603%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%603%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName>|  
|분석기|CD0058|  
  
<a name="diagnostic59"></a>   
## <a name="59-log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a>59: ObjectContext.CreateDatabase 메서드로 만든 로그 파일 이름이 SQL Server 사양에 맞게 변경됩니다  
  
|||  
|-|-|  
|설명|CreateDatabase 메서드를 직접 호출하거나 SqlClient 공급자로 Code First를 사용하고 연결 문자열의 AttachDBFilename 값을 사용하여 호출하면 filename.ldf 대신 filename_log.ldf라는 로그 파일이 생성됩니다(filename이 AttachDBFilename 값으로 지정한 파일 이름인 경우). 이 변경을 통해 SQL Server 사양에 따라 명명된 로그 파일을 제공하여 디버깅을 개선합니다.|  
|제안 해결 방법|로그 파일 이름이 응용 프로그램에서 중요한 경우 응용 프로그램은 표준 _log.ldf 파일 이름 형식을 사용하도록 업데이트되어야 합니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName>|  
|분석기|CD0059|  
  
<a name="diagnostic60"></a>   
## <a name="60-pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a>60: Page.LoadComplete 이벤트는 데이터 바인딩을 호출하기 위해 더 이상 System.Web.UI.WebControls.EntityDataSource 컨트롤을 발생시키지 않습니다  
  
|||  
|-|-|  
|세부 정보|`Page.LoadComplete` 이벤트로 인해 더 이상 System.Web.UI.WebControls.EntityDataSource 컨트롤에서 매개 변수 생성/업데이트/삭제를 위해 변경 내용에 대한 데이터 바인딩을 호출하지 않습니다. 이러한 변경으로 인해 데이터베이스에 대한 불필요한 이동이 제거되고 컨트롤 값이 다시 설정되는 것을 방지하며 SqlDataSource 및 ObjectDataSource 같은 다른 데이터 컨트롤과 일관된 동작을 발생시킵니다. 이러한 변경으로 인해 드물게 응용 프로그램에서 `Page.LoadComplete` 이벤트의 데이터 바인딩 호출을 사용하는 경우 다른 동작이 발생합니다.|  
|제안 해결 방법|데이터 바인딩이 필요한 경우 앞부분에 다시 게시된 이벤트에서 데이터 바인딩을 수동으로 호출합니다.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|분석기|CD0060|  
  
<a name="diagnostic61"></a>   
## <a name="61-webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a>61: WebUtility.HtmlDecode는 잘못된 입력 시퀀스를 더 이상 디코딩하지 않습니다  
  
|||  
|-|-|  
|세부 정보|기본적으로 디코딩 메서드는 더 이상 잘못된 입력 시퀀스를 잘못된 UTF-16 문자열로 디코딩하지 않습니다. 대신, 원래 입력을 반환합니다.|  
|제안 해결 방법|문자열에 UTF-16 데이터 대신 이진 데이터를 저장하는 경우에만 디코더 출력에서의 변경 사항이 문제가 되어야 합니다. 이러한 동작을 명시적으로 제어하려면 [appSettings](https://msdn.microsoft.com/library/ms228154\(v=vs.110\).aspx) 요소의 `aspnet:AllowRelaxedUnicodeDecoding` 특성을 true로 설정하여 레거시 동작을 사용하도록 설정하거나 false로 설정하여 현재 동작을 사용하도록 설정합니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Net.WebUtility.HtmlDecode%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Net.WebUtility.HtmlDecode%28System.String%2CSystem.IO.TextWriter%29?displayProperty=fullName><br /><br /> <xref:System.Net.WebUtility.UrlDecode%28System.String%29?displayProperty=fullName>|  
|분석기|CD0061|  
  
<a name="diagnostic63"></a>   
## <a name="63-apps-published-with-clickonce-that-use-a-sha-256-code-signing-certificate-may-fail-on-windows-2003"></a>63: SHA-256 코드 서명 인증서를 사용하는 ClickOnce로 게시된 앱이 Windows 2003에서 실패할 수 있습니다  
  
|||  
|-|-|  
|세부 정보|실행 파일이 SHA256으로 서명됩니다. 이전에는 코드 서명 인증서가 SHA-1 또는 SHA-256인지에 관계없이 SHA1로 서명되었습니다. 적용 대상:<br /><br /> Visual Studio 2012 이상으로 빌드된 모든 응용 프로그램<br /><br /> .NET Framework 4.5가 있는 시스템에서 Visual Studio 2010 또는 이전 버전으로 빌드된 응용 프로그램<br /><br /> 또한 .NET Framework 4.5 이상이 있는 경우 컴파일 시의 대상 .NET Framework 버전에 관계없이 ClickOnce 매니페스트도 SHA-256 인증서에 대해 SHA-256으로 서명됩니다.|  
|제안 해결 방법|ClickOnce 실행 파일의 서명 변경 내용은 Windows Server 2003 시스템에만 영향을 줍니다. KB 938397을 설치해야 합니다.<br /><br /> 앱이 .NET Framework 4.0 또는 이전 버전을 대상으로 하는 경우에도 SHA-256으로 매니페스트에 서명하는 변경 내용으로 인해 .NET Framework 4.5 이상 버전에서 런타임 종속성이 발생합니다.|  
|범위|Microsoft Edge|  
|버전|4.5-4.6|  
|형식|대상 변경|  
|분석기|CD0063|  
  
<a name="diagnostic68"></a>   
## <a name="68-dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a>68: DbParameter.Precision 및 DbParameter.Scale는 공용 가상 멤버  
  
|||  
|-|-|  
|세부 정보|DbParameter.Precision 및 DbParameter.Scale가 공용 가상 속성으로 구현됩니다. 해당하는 명시적 인터페이스 구현인 DbParameter.IDbDataParameter.Precision 및 DbParameter.IDbDataParameter.Scale을 대체합니다.|  
|제안 해결 방법|ADO.NET 데이터베이스 공급자를 다시 작성할 때 이러한 차이는 전체 자릿수 및 소수 자릿수 속성에 적용될 'override' 키워드가 필요합니다. 이것은 구성 요소를 다시 작성할 때만 필요하며 기존의 이진 파일은 계속 작동합니다.|  
|범위|사소함|  
|버전|4.5.1|  
|형식|대상 변경|  
|영향을 받는 API|<xref:System.Data.Common.DbParameter.Precision?displayProperty=fullName><br /><br /> <xref:System.Data.Common.DbParameter.Scale?displayProperty=fullName>|  
|분석기|CD0068|  
  
<a name="diagnostic73"></a>   
## <a name="73-dataobjectgetdata-now-retrieves-data-as-utf-8"></a>73: DataObject.GetData는 데이터를 UTF-8로 검색  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4를 대상으로 하거나 .NET Framework 4.5.1 이하 버전에서 실행되는 앱의 경우, DataObject.GetData는 HTML 형식의 데이터를 ASCII 문자열로 검색합니다. 그 결과 ASCII 문자가 아닌 문자(ASCII 코드가 0x7F보다 큰 문자)는 임의의 두 문자로 표시됩니다.<br /><br /> .NET Framework 4.5 이상을 대상으로 하거나 .NET Framework 4.5.2에서 실행되는 앱의 경우, `DataObject.GetData`는 HTML 형식의 데이터를 UTF-8로 검색하여 0x7F보다 큰 문자를 올바르게 나타낼 수 있습니다.|  
|제안 해결 방법|HTML 형식 문자열 인코딩 문제에 대한 해결 방법을 구현한 상태에서(예를 들어 클립보드에서 검색한 HTML 문자열을 UTF8Encoding.GetString 메서드에 전달하여 명시적으로 인코딩함으로써) 앱의 대상을 버전 4에서 4.5로 다시 지정하려면 해당 해결 방법을 제거해야 합니다.<br /><br /> 어떤 이유로 이전 동작이 필요한 경우 응용 프로그램은 .NET Framework 4.0을 대상으로 하여 해당 동작을 가져올 수 있습니다.|  
|범위|Microsoft Edge|  
|버전|4.5.2|  
|형식|대상 변경|  
|영향을 받는 API|<xref:System.Windows.DataObject.GetData%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Windows.DataObject.GetData%28System.String%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Windows.DataObject.GetData%28System.Type%29?displayProperty=fullName>|  
|분석기|CD0073|  
  
<a name="diagnostic75"></a>   
## <a name="75-targetframeworkname-for-default-app-domain-no-longer-defaults-to-null-if-not-set"></a>75: 기본 응용 프로그램 도메인에 대한 TargetFrameworkName은 설정하지 않으면 더 이상 null을 기본값으로 하지 않습니다  
  
|||  
|-|-|  
|세부 정보|이전에는 TargetFrameworkName이 명시적으로 설정되지 않은 경우 기본 응용 프로그램 도메인에서 null이었습니다. 4.6부터 기본 응용 프로그램 도메인에 대한 TargetFrameworkName 속성은 TargetFrameworkAttribute에서 파생된 기본값을 가집니다(있는 경우). 기본이 아닌 응용 프로그램 도메인은 명시적으로 재정의되지 않으면 해당 TargetFrameworkName을 기본 응용 프로그램 도메인(4.6에서 기본값을 null로 하지 않는)에서 계속 상속합니다.|  
|제안 해결 방법|코드는 기본값을 null로 하는 `AppDomainSetup.TargetFrameworkName`에 종속하지 않도록 업데이트되어야 합니다. 이 속성이 계속 null을 평가해야 하는 경우 명시적으로 해당 값을 설정할 수 있습니다.|  
|범위|Microsoft Edge|  
|버전|4.6|  
|형식|런타임|  
|영향을 받는 API|<xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName>|  
|분석기|CD0075B<br /><br /> CD0075A|  
  
<a name="diagnostic76"></a>   
## <a name="76-x509certificate2tostringbool-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>76: X509Certificate2.ToString(bool)은 .NET이 인증서를 처리할 수 없을 때 throw하지 않습니다  
  
|||  
|-|-|  
|설명|이전에는 ‘true’가 verbose 매개 변수에 전달되면 이 메서드가 throw했으며 .Net Framework가 지원하지 않는 인증서가 설치되었습니다. 이제 메서드는 인증서의 액세스할 수 없는 부분을 생략하는 유효한 문자열을 성공하고 반환합니다.|  
|제안 해결 방법|X509Certificate2.ToString(bool)에 종속된 모든 코드는 API가 이전에 throw된 일부 경우에서 반환된 문자열이 일부 인증서 데이터(예: 공개 키, 개인 키 및 확장명)를 제외하도록 업데이트되어야 합니다.|  
|범위|Microsoft Edge|  
|버전|4.6|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString%28System.Boolean%29?displayProperty=fullName>|  
|분석기|CD0076|  
  
<a name="diagnostic77"></a>   
## <a name="77-reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>77: 더 이상 리플렉션 개체를 관리 코드에서 out-of-process DCOM 클라이언트로 전달할 수 없습니다  
  
|||  
|-|-|  
|세부 정보|더이상 리플렉션 개체를 관리 코드에서 out-of-process DCOM 클라이언트로 전달할 수 없습니다. 다음 형식이 영향을 받습니다.<br /><br /> Assembly<br /><br /> MemberInfo (및 FieldInfo, MethodInfo, Type 및 TypeInfo를 포함하는 파생 형식)<br /><br /> MethodBody<br /><br /> 모듈<br /><br /> ParameterInfo.<br /><br /> 개체에 대한 `IMarshal`을 호출하면 `E_NOINTERFACE`를 반환합니다.|  
|제안 해결 방법|마샬링 코드를 리플렉션이 아닌 개체를 사용하도록 업데이트|  
|범위|사소함|  
|버전|4.6|  
|형식|런타임|  
|분석기|CD0077|  
  
<a name="diagnostic78"></a>   
## <a name="78-contentdisposition-datetimes-returns-slightly-different-string"></a>78: ContentDisposition DateTimes는 약간 다른 문자열을 반환합니다  
  
|||  
|-|-|  
|세부 정보|4.6부터 ContentDispositions의 문자열 표현이 항상 DateTime의 구성 요소를 두 자리로 표시하도록 업데이트되었습니다. 이것은 [RFC822](http://www.ietf.org/rfc/rfc0822.txt) 및 [RFC2822](http://www.ietf.org/rfc/rfc2822.txt)를 준수하기 위함입니다. 이로 인해 4.6에서 `ContentDisposition.ToString`은 처리 시간 요소 중 하나가 오전 10시 전인 시나리오에서 약간 다른 문자열을 반환합니다. ContentDispositions는 가끔 문자열로 변환하여 직렬화되므로 모든 ContentDisposition ToString 작업, 직렬화 또는 GetHashCode 호출이 검토되어야 합니다.|  
|제안 해결 방법|다른 .NET Framework 버전에서 ContentDispositions의 문자열 표현이 서로 올바르게 비교할 것으로 기대하지 마십시오. 가능하면 비교를 수행하기 전에 문자열을 다시 ContentDispositions로 변환합니다.|  
|범위|사소함|  
|버전|4.6|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=fullName><br /><br /> <xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=fullName>|  
|분석기|CD0078|  
  
<a name="diagnostic82"></a>   
## <a name="82-workflowdesignerload-doesnt-remove-symbol-property"></a>82: WorkflowDesigner.Load는 기호 속성을 제거하지 않습니다  
  
|||  
|-|-|  
|세부 정보|Workflow Designer에서 .NET Framework 4.5를 대상으로 하고 WorkflowDesigner.Load() 메서드를 사용하여 다시 호스트된 3.5 워크플로를 로드하면 워크플로를 저장하는 동안 XamlDuplicateMemberException이 throw됩니다.|  
|제안 해결 방법|이 버그는 Workflow Designer에서 .NET Framework 4.5를 대상으로 할 때에 매니페스트되므로 `WorkflowDesigner.Context.Services.GetService<DesignerConfigurationService>().TargetFrameworkName`을 .NET Framework 4.0로 설정하여 해결할 수 있습니다.<br /><br /> 또는 [WorkflowDesigner.Load()](https://msdn.microsoft.com/library/ee403482\(v=vs.110\).aspx) 대신 [WorkflowContext.Load(string)](https://msdn.microsoft.com/library/ee425926\(v=vs.110\).aspx) 메서드를 사용하여 워크플로를 로드하면 문제를 피할 수 있습니다.|  
|범위|주요함|  
|버전|4.5-4.5.2|  
|형식|대상 변경|  
|영향을 받는 API|<xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=fullName>|  
|분석기|CD0082|  
  
<a name="diagnostic83"></a>   
## <a name="83-sqlconnectionopen-fails-on-windows-7-with-non-ifs-winsock-bsp-or-lsp-present"></a>83: SqlConnection.Open은 비 IFS Winsock BSP 또는 LSP가 있는 Windows 7에서 실패  
  
|||  
|-|-|  
|세부 정보|비 IFS Winsock BSP 또는 LSP를 사용하는 Windows 7 컴퓨터에서 실행 중인 경우 SqlConneciton.Open 및 OpenAsync는 .NET Framework 4.5에서 실패합니다.<br /><br /> 비 IFS BSP 또는 LSP가 설치되어 있는지를 확인하려면 `netsh WinSock Show Catalog` 명령을 사용하여 반환되는 모든 `Winsock Catalog Provider Entry` 항목을 검사합니다. 서비스 플래그 값이 `0x20000` 비트 집합을 가진 경우, 공급자는 IFS 핸들을 사용하고 올바르게 작동합니다. `0x20000` 비트가 지우기인 경우(집합 아님) 비 IFS BSP 또는 LSP입니다.|  
|제안 해결 방법|이 버그는 .NET Framework 4.5.2에서 수정되었으므로 .NET Framework를 업그레이드하여 방지할 수 있습니다. 또는 설치된 모든 비 IFS Winsock LSP를 제거하여 방지할 수 있습니다.|  
|범위|사소함|  
|버전|4.5-4.5.2|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=fullName><br /><br /> <xref:System.Data.SqlClient.SqlConnection.OpenAsync%28System.Threading.CancellationToken%29?displayProperty=fullName>|  
|분석기|CD0083|  
  
<a name="diagnostic84"></a>   
## <a name="84-icommandcanexecutechanged-event-behaviour-changed-in-net-45"></a>84: .NET 4.5에서 ICommand.CanExecuteChanged 이벤트 동작 변경됨  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.5에서 이벤트를 보낸 사람이 이벤트를 발생시킨 개체와 같은 개체가 아닌 이상 CanExecuteChangedEvent는 무시되었습니다. 이 버그는 .NET Framework 4.5 서비스 업데이트에서 수정되었습니다.|  
|제안 해결 방법|이 버그는 .NET Framework 4.5 서비스 릴리즈에서 수정되었으므로 .NET Framework가 최신 버전인지 확인하거나 .NET Framework 4.5.1로 업데이트하여 방지할 수 있습니다. 또는 CanExecuteChanged 명령을 발생시킬 때 보낸 사람이 이벤트를 발생시키는 개체와 동일한 지 확인하도록 ICommand를 사용하는 응용 프로그램 코드를 수정할 수 있습니다.|  
|범위|사소함|  
|버전|4.5-4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=fullName>|  
|분석기|CD0084|  
  
<a name="diagnostic85"></a>   
## <a name="85-some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a>85: 일부 .NET API는 첫 번째 기회(처리됨) EntryPointNotFoundExceptions를 발생시킵니다  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.5에서 작은 수의 .NET 메서드가 첫 번째 기회 EntryPointNotFoundExceptions를 throw하기 시작했습니다. 이러한 예외는 .Net Framework 내에서 처리되지만 첫 번째 예외를 예상하지 않은 테스트 자동화를 중단시킬 수 있습니다. 이러한 동일 API는 HighVersionLie를 사용하는 경우 일부 ApiVerifier 시나리오를 중단시킵니다.|  
|제안 해결 방법|.NET Framework 4.5.1로 업그레이드하여 이 버그를 방지할 수 있습니다. 또는 첫 번째 EntryPointNotFoundExceptions에서 중단되지 않도록 테스트 자동화를 업데이트할 수 있습니다.|  
|범위|Microsoft Edge|  
|버전|4.5-4.5.1|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Diagnostics.Debug.Assert%28System.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%29?displayProperty=fullName>|  
|분석기|CD0085|  
  
<a name="diagnostic86"></a>   
## <a name="86-scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a>86: ListBoxVirtualizingStackPanel에서 WPF TreeView 또는 그룹화된 ListBox를 스크롤하면 중단될 수 있습니다  
  
|||  
|-|-|  
|설명|.NET Framework v4.5에서 뷰포트에 여백이 있는 경우 가상화된 스택 패널의 WPF TreeView를 스크롤하면 중단이 발생할 수 있습니다(예: 항목 간 TreeView 또는 ItemsPresenter 요소). 또한 일부 경우에는 보기에서 다양한 크기의 항목은 여백이 없더라도 불안정해 보일 수 있습니다.|  
|제안 해결 방법|.NET Framework 4.5.1로 업그레이드하여 이 버그를 방지할 수 있습니다. 또는 포함된 모든 항목이 같은 크기인 경우 가상화된 스택 패널 내에서 여백을 보기 컬렉션(예: Treeview)으로부터 제거할 수 있습니다.|  
|범위|주요함|  
|버전|4.5-4.5.1|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Windows.Controls.VirtualizingPanel.SetIsVirtualizing%28System.Windows.DependencyObject%2CSystem.Boolean%29?displayProperty=fullName>|  
|분석기|CD0086<br /><br /> CD0086|  
  
<a name="diagnostic89"></a>   
## <a name="89-typeisassignablefrom-returns-wrong-result-for-generic-variables-with-constraints"></a>89: Type.IsAssignableFrom는 제약 조건이 있는 제네릭 변수에 대해 잘못된 결과를 반환합니다  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.5에서 Type.IsAssignableFrom은 제약 조건이 있는 일부 제네릭 형식의 제약 조건에 대한 모든 경우에서 `false`를 잘못 반환합니다.|  
|제안 해결 방법|이 문제는 서비스 업데이트에서 수정되었습니다. 이 문제를 해결하려면 .NET Framework 4.5를 업데이트하거나 .NET Framework 4.5.1 이상으로 업그레이드하십시오. 또는 제네릭 매개 변수에 대해 제약 조건이 있는 제네릭 형식으로 IsAssignableFrom을 사용하지 마십시오. 리플렉션 API는 해결 방법으로 사용될 수 있습니다.|  
|범위|사소함|  
|버전|4.5-4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Type.IsAssignableFrom%28System.Type%29?displayProperty=fullName>|  
|분석기|CD0089<br /><br /> CD0089|  
  
<a name="diagnostic91"></a>   
## <a name="91-entityframework-60-loads-very-slowly-in-apps-launched-from-visual-studio"></a>91: EntityFramework 6.0은 Visual Studio에서 시작된 앱에서 매우 느리게 로드합니다.  
  
|||  
|-|-|  
|세부 정보|EntityFramework 6.0을 사용하는 Visual Studio 2013에서 응용 프로그램을 시작하면 매우 느릴 수 있습니다.|  
|제안 해결 방법|이 문제는 EntityFramework 6.0.2에서 수정되었습니다. 성능 문제를 방지하려면 EntityFramework를 업데이트하십시오.|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|분석기|CD0091|  
  
<a name="diagnostic92"></a>   
## <a name="92-multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a>92: AntiXSSEncoder를 사용할 때 여러 줄 ASP.Net TextBox 간격이 변경됩니다.  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.0에서 `AntiXSSEncoder`을 사용하는 경우 추가 줄은 포스트백에서 여러 줄 텍스트 상자의 줄 사이에 삽입되었습니다. .NET Framework 4.5에서는 웹 응용 프로그램이 .NET 4.5를 대상으로 하는 경우를 제외하고 이러한 추가 줄 바꿈이 포함되지 않습니다.|  
|제안 해결 방법|.NET 4.5로 대상이 다시 지정된 4.0 웹 응용 프로그램에는 더 이상 추가 줄 바꿈을 삽입하지 않도록 개선된 여러 줄 텍스트 상자가 있을 수 있습니다. 이것이 필요 없는 경우 응용 프로그램은 .NET Framework 4.0을 대상으로 하여 .NET Framework 4.5에서 실행하는 경우 이전 동작을 할 수 있습니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|대상 변경|  
|분석기|CD0092|  
  
<a name="diagnostic95"></a>   
## <a name="95-concurrentqueuettrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>95: ConcurrentQueue\<T>.TryPeek는 out 매개 변수를 통해 잘못된 null을 반환할 수 있습니다.  
  
|||  
|-|-|  
|설명|일부 다중 스레드 시나리오에서 `ConcurentQueue<T>.TryPeek` true를 반환할 수 있지만 (올바르고 미리 본 값 대신) null 값으로 out 매개 변수를 채웁니다.|  
|제안 해결 방법|이 문제는 .NET Framework 4.5.1에서 수정되었습니다. 해당 프레임워크로 업그레이드하면 문제가 해결됩니다.|  
|범위|주요함|  
|버전|4.5-4.5.1|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek%28%600%40%29?displayProperty=fullName>|  
|분석기|CD0095|  
  
<a name="diagnostic98"></a>   
## <a name="98-multiple-items-in-a-single-tablelayoutpanel-cell-may-be-rearranged"></a>98: 단일 TableLayoutPanel 셀에 있는 여러 항목이 다시 배열될 수 있습니다.  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.5에서 여러 항목이 동일한 TableLayoutPanel 셀에 배치된 경우 .NET Framework 4.0에서와 다른 순서로 표시될 수 있습니다.|  
|제안 해결 방법|이 동작은 .NET Framework 4.5에 대한 서비스 업데이트에서 되돌려졌습니다. 이 문제를 해결하려면 .NET Framework 4.5를 업데이트하거나 .NET Framework 4.5.1 이상으로 업그레이드하십시오. 또는 동일한 TableLayourPanel 셀에서 여러 항목의 모호한 경우를 사용하지 마십시오.|  
|범위|사소함|  
|버전|4.5-4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Windows.Forms.TableLayoutControlCollection.Add%28System.Windows.Forms.Control%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|분석기|CD0098|  
  
<a name="diagnostic100"></a>   
## <a name="100-foreach-iterator-variable-is-now-scoped-within-the-iteration-so-closure-capturing-semantics-are-different-in-c5"></a>100: 이제 Foreach 반복기 변수는 반복 내에 범위가 지정되어 의미 체계를 캡처하는 클로저가 다릅니다(C#5에서).  
  
|||  
|-|-|  
|세부 정보|C# 5(Visual Studio 2012)부터 foreach 반복기 변수는 반복 내에서 범위가 지정됩니다. 이것은 코드가 이전에 foreach의 클로저에 포함되지 않기 위해 변수에 종속되었던 경우 중단이 발생할 수 있습니다. 이러한 변경의 증상은 반복기 변수로 대리자에게 전달되고 대리자가 호출된 때의 값이 아닌 대리자가 생성된 때의 값으로 간주됩니다.|  
|제안 해결 방법|이상적으로 코드는 새 컴파일러 동작을 예상하도록 업데이트되어야 합니다. 이전의 의미 체계가 필요한 경우 반복기 변수는 루프 외부에 명시적으로 배치된 별도의 변수로 대체할 수 있습니다.|  
|범위|주요함|  
|버전|4.5|  
|형식|대상 변경|  
|분석기|CD0100|  
  
<a name="diagnostic101"></a>   
## <a name="101-htmltextwriter-does-not-render-br-element-correctly"></a>101: HtmlTextWriter는 \`<br/\> 요소를 올바르게 렌더링하지 않습니다.  
  
|||  
|-|-|  
|설명|.NET Framework 4.6부터 `<BR />` 요소로 `HtmlTextWriter.RenderBeginTag()` 및 `HtmlTextWriter.RenderEndTag()`를 호출하면 (두 개가 아닌) 단 하나의 `<BR />`만 올바르게 삽입합니다.|  
|제안 해결 방법|응용 프로그램이 추가 `<BR />` 태그에 종속된 경우 `HtmlTextWriter.RenderBeginTag()`를 두 번째로 호출해야 합니다. 이 동작 변경은 .NET Framework 4.6을 대상으로 하는 응용 프로그램에만 영향을 주므로 다른 옵션은 이전 버전의 .NET Framework를 대상으로 하여 이전 동작을 가져오는 것입니다.|  
|범위|Microsoft Edge|  
|버전|4.6|  
|형식|대상 변경|  
|영향을 받는 API|<xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName>|  
|분석기|CD0101|  
  
<a name="diagnostic104"></a>   
## <a name="104-calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>104: 항목이 선택된 WPF ListBox, ListView, 또는 DataGrid에서 Items.Refresh를 호출하면 요소에 중복 항목이 표시될 수 있습니다.  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.5에서 항목이 ListBox에 선택되어 있을 때 ListBox.Items.Refresh 코드를 호출하면 선택된 항목이 목록에 중복되는 것을 야기할 수 있습니다. ListView와 DataGrid에서 유사한 문제가 발생합니다. 이것은 .NET Framework 4.6에서 수정되었습니다.|  
|제안 해결 방법|이 문제는 Refresh를 호출하기 전에 프로그래밍 방식으로 항목 선택을 취소하고 호출이 완료된 후에 다시 선택하여 해결할 수 있습니다. 또는 .NET Framework 4.6에서 이 문제가 수정되어 해당 버전의 .NET Framework로 업그레이드하여 해결할 수 있습니다.|  
|범위|사소함|  
|버전|4.5-4.6|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName>|  
|분석기|CD0104|  
  
<a name="diagnostic105"></a>   
## <a name="105-etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a>105: ETW EventListeners는 명시적 키워드를 사용하는 공급자의 이벤트를 캡처하지 않습니다(예: TPL 공급자).  
  
|||  
|-|-|  
|설명|빈 키워드 마스크가 있는 ETW EventListeners는 명시적 키워드를 사용하는 공급자의 이벤트를 제대로 캡처하지 않습니다. .NET Framework 4.5에서 TPL 공급자는 명시적 키워드를 제공하기 시작했고 이 문제를 트리거했습니다. .NET Framework 4.6에서 더 이상 이 문제가 발생하지 않도록 EventListeners 업데이트되었습니다.|  
|제안 해결 방법|이 문제를 해결하려면 EnableEvents(eventSource, level) 호출을 “모든 키워드” 마스크가 `EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))`을 사용하도록 명시적으로 지정하는 EnableEvents 오버로드 호출로 바꿉니다.<br /><br /> 또는 .NET Framework 4.6에서 이 문제가 수정되어 해당 버전의 .NET Framework로 업그레이드하여 해결할 수 있습니다.|  
|범위|Microsoft Edge|  
|버전|4.5-4.6|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%29?displayProperty=fullName>|  
|분석기|CD0105|  
  
<a name="diagnostic109"></a>   
## <a name="109-building-an-entity-framework-edmx-with-visual-studio-2013-can-fail-with-error-msb4062-if-using-the-entitydeploysplit-or-entityclean-tasks"></a>109: Visual Studio 2013을 사용하여 Entity Framework edmx를 빌드할 때 EntityDeploySplit 또는 EntityClean 작업을 사용하면 MSB4062 오류로 실패할 수 있습니다.  
  
|||  
|-|-|  
|세부 정보|MSBuild 12.0 도구(Visual Studio 2013 포함)가 msbuild 파일 위치를 변경하여 이전 Entity Framework 대상 파일을 유효하지 않게 했습니다. 그 결과로 `EntityDeploySplit` 및 `EntityClean` 작업이 `Microsoft.Data.Entity.Build.Tasks.dll`을 찾을 수 없어 실패합니다. 이 줄바꿈은 .NET Framework의 변경 때문이 아닌 도구 집합(msbuild/VS) 변경 때문입니다. 이것은 단순히 .NET Framework를 업그레이드할 때가 아니라 개발자 도구를 업그레이드할 때에만 발생합니다.|  
|제안 해결 방법|.NET Framework 4.6부터 Entity Framework 대상 파일은 새 msbuild 레이아웃으로 작업하도록 수정되었습니다. 해당 버전의 Framework로 업그레이드하면 이 문제가 해결됩니다. 또는 [이](http://stackoverflow.com/a/24249247/131944) 해결 방법을 대상 파일을 직접 패치하는데 사용할 수 있습니다.|  
|범위|주요함|  
|버전|4.5.1-4.6|  
|형식|대상 변경|  
|분석기|CD0109|  
  
<a name="diagnostic111"></a>   
## <a name="111-xsd-schema-validation-now-correctly-detects-violations-of-unique-constraints-if-compound-keys-are-used-and-one-key-is-empty"></a>111: 복합 키를 사용하고 하나의 키가 비어 있는 경우 XSD 스키마 유효성 검사는 이제 올바르게 UNIQUE 제약 조건 위반을 감지합니다.  
  
|||  
|-|-|  
|설명|.NET Framework 4.6 이전 버전은 키 중 하나가 비어있는 경우 XSD 유효성 검사가 복합 키에서 UNIQUE 제약 조건을 감지하지 않는 버그가 있었습니다. .NET Framework 4.6에서 이 문제가 수정되었습니다. 이렇게 하면 보다 정확한 유효성 검사가 되지만 이전에 검사되었던 일부 XML이 유효성 검사되지 않는 결과를 발생시킬 수 있습니다.|  
|제안 해결 방법|완화된 .NET Framework 4.0 유효성 검사가 필요한 경우 유효성 검사 응용 프로그램은 .NET Framework 4.5(또는 이전) 버전을 대상으로 할 수 있습니다. 하지만 .NET 4.6으로 다시 대상을 지정하는 경우 중복 복합 키가 (이 문제 설명에 기술된 것처럼) 유효성 검사되지 않도록 코드 검토를 수행해야 합니다.|  
|범위|Microsoft Edge|  
|버전|4.6|  
|형식|대상 변경|  
|분석기|CD0111|  
  
<a name="diagnostic112"></a>   
## <a name="112-calling-attributegetcustomattributes-on-an-indexer-property-no-longer-throws-ambiguousmatchexception-if-the-ambiguity-can-be-resolved-by-indexs-type"></a>112: 인덱스 형식으로 모호성이 해결될 수 있는 경우 인덱서 속성에서 Attribute.GetCustomAttributes를 호출하면 더 이상 AmbiguousMatchException을 throw하지 않습니다.  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.6 전에는 인덱스의 형식만 다른 속성과 다른 인덱서 속성에서 `GetCustomAttribute(s)`을 호출하면 `AmbiguousMatchException`에 결과가 발생했습니다. .NET Framework 4.6부터 속성의 특성이 올바르게 반환됩니다.|  
|제안 해결 방법|이제 GetCustomAttribute가 더 자주 작동한다는 것을 기억하십시오. 응용 프로그램이 이전에 `AmbiguousMatchException`을 의존한 경우 리플렉션은 대신 다중 인덱서를 명시적으로 찾는 데 사용되어야 합니다.|  
|범위|Microsoft Edge|  
|버전|4.6|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Attribute.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName>|  
|분석기|CD0112|  
  
<a name="diagnostic113"></a>   
## <a name="113-intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a>113: 사용자 지정 Datatemplate를 사용하는 경우 일시적으로 ItemsControls에서(예: ListBox 및 DataGrid) 하위 항목으로 스크롤할 수 없습니다.  
  
|||  
|-|-|  
|세부 정보|일부 인스턴스에서 .NET Framework 4.5의 버그는 사용자 지정 DataTemplates를 사용할 때 ItemsControls(예: ListBox, ComboBox, DataGrid 등)가 아래 항목을 사용자 지정 Datatemplate를 사용하는 경우 스크롤하지 않게 합니다. 스크롤이 두 번째 시도되는 경우(스크롤 백업 후) 그때에는 작동합니다.|  
|제안 해결 방법|.NET Framework 4.5.2에서 이 문제가 수정되어 해당 버전(또는 이후 버전)의 .NET Framework로 업그레이드하여 해결할 수 있습니다. 또는 사용자가 이러한 컬렉션의 마지막 항목까지 스크롤 막대를 끌 수 있지만 성공하려면 두 번 시도해야 할 수 있습니다.|  
|범위|사소함|  
|버전|4.5-4.5.2|  
|형식|런타임|  
|분석기|CD0113|  
  
<a name="diagnostic114"></a>   
## <a name="114-glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-45"></a>114: .NET 4.5 부터 GlyphRun.ComputeInkBoundingBox() 및 FormattedText.Extent이 다른 값을 반환합니다.  
  
|||  
|-|-|  
|설명|.NET Framework 4.0의 일부 경우에서 포함된 문자 모양에 대해 상자가 너무 작은 문제를 해결하기 휘애 .NET Framework 4.5에서 GlyphRun.ComputeInkBoundingBox() 및 FormattedText.Extent를 개선하였습니다. 결과적으로 .NET Framework 4.5부터 일부 경계 상자가 커져 UI 레이아웃에 미묘한 차이가 발생합니다.|  
|제안 해결 방법|일부 문자 모양 경계 상자의 크기가 커졌습니다. 이러한 변경은 일반적으로 프레젠테이션 및 적중 상자 테스트를 향상시키지만 이전 동작(.NET 4.5 전)이 필요할 경우 app.config 파일에 다음의 항목을 추가하여 사용할 수 있습니다.<br /><br /> `<appsettings> <add key="IncludeAllInkInBoundingBox" value="false"> </appsettings>`|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=fullName><br /><br /> <xref:System.Windows.Media.FormattedText.Extent?displayProperty=fullName>|  
|분석기|CD0114|  
  
<a name="diagnostic124"></a>   
## <a name="124-calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a>124: CellEditEnding 처리기에서 DataGrid.CommitEdit를 호출하여 포커스를 삭제합니다.  
  
|||  
|-|-|  
|세부 정보|DataGrid의 CellEditEnding 이벤트 처리기 중 하나에서 DataGrid.CommitEdit를 호출하면 DataGrid가 포커스를 잃습니다.|  
|제안 해결 방법|이 버그는 .NET Framework 4.5.2에서 수정되었으므로 .NET Framework를 업그레이드하여 방지할 수 있습니다. 또는 CommitEdit를 호출한 후에 다시 DataGrid를 명시적으로 선택하여 방지할 수 있습니다.|  
|범위|Microsoft Edge|  
|버전|4.5-4.5.2|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName><br /><br /> <xref:System.Windows.Controls.DataGrid.CommitEdit%28System.Windows.Controls.DataGridEditingUnit%2CSystem.Boolean%29?displayProperty=fullName>|  
|분석기|CD0124|  
  
<a name="diagnostic125"></a>   
## <a name="125-aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a>125: ASP.NET MVC는 이제 경로 매개 변수를 통해 전달된 문자열에 있는 공백을 이스케이프합니다.  
  
|||  
|-|-|  
|설명|RFC 2396를 준수하려면 경로에서 작업 매개 변수를 채울 때 경로의 공백은 이스케이프됩니다. 따라서 이전에는 `/controller/action/some data`이 경로 `/controller/action/{data}`와 일치하고 `some data`를 데이터 매개 변수로 제공했지만 이제는 `some%20data`를 대신 제공합니다.|  
|제안 해결 방법|경로에서 문자열 매개 변수를 이스케이프 해제하려면 코드를 업데이트해야 합니다. 원래의 URI가 필요한 경우 Request.RequestUri.OriginalString API를 통해 액세스할 수 있습니다.|  
|범위|사소함|  
|버전|4.5.2|  
|형식|런타임|  
|영향을 받는 API|[System.Web.Http.RouteAttribute](https://msdn.microsoft.com/library/system.web.http.routeattribute(v=vs.118).aspx)|  
|분석기|CD0125|  
  
<a name="diagnostic127"></a>   
## <a name="127-vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a>127: VB.NET는 System.Windows API에 대한 부분 네임스페이스 한정을 더 이상 지원하지 않습니다.  
  
|||  
|-|-|  
|세부 정보|.NET 4.5.2부터 VB.NET 프로젝트는 부분적으로 정규화된 네임스페이스를 사용하는 System.Windows API를 지정할 수 없습니다. 예를 들어 `Windows.Forms.DialogResult`를 참조하면 실패합니다. 대신, 코드는 정규화된 이름(`System.Windows.Forms.DialogResult`)을 참조하거나 특정 네임스페이스를 가져오고 간단히 `DialogResult`를 참조해야 합니다.|  
|제안 해결 방법|코드는 간단한 이름(및 관련 네임스페이스를 가져오는) 또는 정규화된 이름을 사용하는 `System.Windows` API를 참조하도록 업데이트되어야 합니다.|  
|범위|사소함|  
|버전|4.5.2|  
|형식|대상 변경|  
|분석기|CD0127|  
  
<a name="diagnostic129"></a>   
## <a name="129-two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a>129: Public이 아닌 setter를 사용하는 속성에 양방향 데이터 바인딩을 지원하지 않습니다.  
  
|||  
|-|-|  
|세부 정보|public setter가 없는 속성에 데이터 바인딩을 시도하는 것은 지원된 적이 없는 시나리오였습니다. .NET Framework 4.5.1부터는 이 시나리오가 InvalidOperationException을 throw합니다. 이 새로운 예외는 구체적으로 .NET Framework 4.5.1을 대상으로 하는 응용 프로그램만 throw됩니다. 응용 프로그램이 .NET Framework 4.5를 대상으로 하는 경우 호출이 허용됩니다. 응용 프로그램이 특정 .NET Framework 버전을 대상으로 하지 않는 경우 바인딩은 단방향으로 처리됩니다.|  
|제안 해결 방법|응용 프로그램은 단방향 바인딩을 사용하거나 속성의 setter를 공개적으로 노출하도록 업데이트되어야 합니다. 또는 .NET Framework 4.5를 대상으로 하면 응용 프로그램이 이전 동작을 실행하게 됩니다.|  
|범위|사소함|  
|버전|4.5.1|  
|형식|대상 변경|  
|영향을 받는 API|<xref:System.Windows.Data.BindingMode?displayProperty=fullName>|  
|분석기|CD0129|  
  
<a name="diagnostic130"></a>   
## <a name="130-marshalsizeof-and-marshalptrtostructure-overloads-break-dynamic-code"></a>130: Marshal.SizeOf와 Marshal.PtrToStructure 오버로드가 동적 코드를 중단시킵니다.  
  
|||  
|-|-|  
|설명|.NET Framework 4.5.1부터 `Marshal.SizeOf` 또는 `Marshal.PtrToStructure` 메서드에 동적으로 바인딩하면 (예: Windows PowerShell, IronPython 또는 C# dynamic 키워드를 통해) 이러한 메서드의 새 오버로드가 추가되어 스크립팅 엔진 모호할 수 있으므로 `MethodInvocationExceptions`을 발생시킬 수 있습니다.|  
|제안 해결 방법|오버로드가 사용되어야 하는 스크립트를 명확히 표시하도록 업데이트합니다. 이것은 일반적으로 메서드의 형식 매개 변수를 `System.Type`로 명시적 캐스팅하여 수행할 수 있습니다. 문제를 해결하는 예제와 자세한 정보는 [이 링크](https://support.microsoft.com/kb/2909958/)를 참조하십시오.|  
|범위|사소함|  
|버전|4.5.1|  
|형식|런타임|  
|분석기|CD0130|  
  
<a name="diagnostic131"></a>   
## <a name="131-previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a>131: PreviewLostKeyboardFocus는 처리기가 Windows Forms 메시지 상자를 표시하는 경우 반복적으로 호출됩니다.  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.5부터 `UIElement.PreviewLostKeyboardFocus` 처리기에서 `System.Windows.Forms.MessageBox.Show`를 호출하면 메시지 상자가 닫힐 때 처리기가 다시 발생하여 잠재적으로 메시지 상자의 무한 루프를 발생시킵니다.|  
|제안 해결 방법|이 문제는 다음 두 가지 옵션으로 해결할 수 있습니다.<br /><br /> 이것은 `System.Windows.Forms.MessageBox.Show` 대신 `System.Windows.MessageBox.Show`를 호출하여 방지할 수 있습니다.<br /><br /> 이것은 `LostKeyboardFocus` 이벤트 처리기에서 메시지 박스를 표시하여 방지할 수 있습니다(`PreviewLostKeyboardFocus` 이벤트 처리기와 반대).|  
|범위|Microsoft Edge|  
|버전|4.5|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=fullName>|  
|분석기|CD0131|  
  
<a name="diagnostic133"></a>   
## <a name="133-a-concurrentdictionary-serialized-in-net-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-451-or-452"></a>133: .NET 4.5에서 NetDataContractSerializer로 직렬화된 ConcurrentDictionary는 .NET 4.5.1 또는 4.5.2에서 역직렬화될 수 없습니다.  
  
|||  
|-|-|  
|세부 정보|형식의 내부 변경 내용으로 인해 `NetDataContractSerializer`를 사용하는 .NET Framework 4.5로 직렬화되는 `System.Collections.Concurrent.ConcurrentDictionary` 개체는 .NET Framework 4.5.1 또는.NET Framework 4.5.2에서 역직렬화될 수 없습니다.<br /><br /> 다른 방향으로의 이동(.NET Framework 4.5.x로 직렬화하고 .NET Framework 4.5로 역직렬화)도 실행됩니다. 마찬가지로 .NET Framework 4.6으로 모든 4.x 버전간 직렬화가 실행됩니다.<br /><br /> 단일 버전의 .NET Framework로 직렬화 및 역직렬화하는 것은 영향을 받지 않습니다.|  
|제안 해결 방법|.NET Framework 4.5와 .NET Framework 4.5.1/4.5.2 사이에서 직렬화 및 역직렬화가 필요한 경우, DataContractSerializer 또는 BinaryFormatter 직렬 변환기 같은 대안 변환기가 NetDataContractSerializer 대신에 사용됩니다.<br /><br /> 또는 .NET Framework 4.6에서 이 문제가 해결되므로 해당 버전의 .NET Framework로 업그레이드하여 해결할 수 있습니다.|  
|범위|사소함|  
|버전|4.5.1-4.6|  
|형식|런타임|  
|분석기|CD0133|  
  
<a name="diagnostic134"></a>   
## <a name="134-persian-calendar-now-uses-the-hijri-solar-algorithm"></a>134: 이제 페르시아력이 회교식 양력 알고리즘을 사용합니다.  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.6부터는 PersianCalendar 클래스에서 회교식 양력 알고리즘을 사용합니다. .NET Framework 4.6부터 PersianCalendar와 다른 달력 간의 날짜 변환은 1800년 전 또는 2023년 후에 대한 날짜에 대해(그레고리오력) 약간 다른 결과를 생성할 수 있습니다.<br /><br /> 또한 이제 `PersianCalendar.MinSupportedDateTime` `March 22, 0622 instead of March 21, 0622`입니다.|  
|제안 해결 방법|.NET 4.6에서 PersianCalendar를 사용할 때 일부 이전 또는 늦은 날짜는 약간 다를 수 있습니다. 또한 다른 .NET Framework 버전에서 실행될 수 있는 프로세스 사이의 날짜를 직렬화할 때 PersianCalendar 날짜 문자열로 저장하지 마십시오(해당 값이 다를 수 있음).|  
|범위|사소함|  
|버전|4.6|  
|형식|런타임|  
|영향을 받는 API|<xref:System.Globalization.PersianCalendar?displayProperty=fullName>|  
|분석기|CD0134|  
  
<a name="diagnostic138"></a>   
## <a name="138-calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a>138: Null 인수를 사용한 CreateDefaultAuthorizationContext 호출이 변경되었습니다.  
  
|||  
|-|-|  
|설명|Null authorizationPolicies를 사용하는 `CreateDefaultAuthorizationContext(IList<IAuthorizationPolicy>)`에 대한 호출로 반환된 AuthorizationContext의 구현이 .NET Framework 4.6에서 변경되었습니다.|  
|제안 해결 방법|드문 경우이지만 사용자 지정 인증을 사용하는 WCF 앱은 다르게 동작할 수 있습니다. 이러한 경우 두 가지 방법 중 하나로 이전 동작을 복원할 수 있습니다.<br /><br /> 4.6 이전 버전의 .NET Framework를 대상으로 사용하도록 앱을 다시 컴파일합니다. IIS 호스트 서비스의 경우 이전 버전의 .NET Framework를 대상으로 하는 \<httpRuntime targetFramework="x.x" /> 요소를 사용합니다.<br /><br /> 다음 줄을 app.config 파일의 `<appSettings>` 섹션에 추가합니다. `<add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />`|  
|범위|사소함|  
|버전|4.6|  
|형식|대상 변경|  
|영향을 받는 API|<xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29?displayProperty=fullName>|  
|분석기|CD0138|  
  
<a name="diagnostic141"></a>   
## <a name="141-wpf-treeviewitem-must-be-used-within-a-treeview"></a>141: TreeView 내에서 WPF TreeViewItem을 사용해야 합니다.  
  
|||  
|-|-|  
|설명|변경 내용은 TreeView의 외부에서 TreeViewItem 요소의 사용을 제한하는 4.5에서 도입되었습니다. 이것은 다음과 같은 경우에 매니페스트할 수 있습니다.<br /><br /> TreeViewItem의 시각적 부모는 패널이 아닙니다. (TreeView에 대해 생성된 TreeViewItem은 패널을 부모로 가집니다.)<br /><br /> TreeViewItem은 목록 컨트롤(ListBox, DataGrid, ListView 등)에 대해 “항목 호스트” 역할을 하는 VirtualizingStackPanel의 하위 항목입니다. 가상화를 사용할 필요가 없습니다.<br /><br /> VirtualizingStackPanel은 항목 스크롤입니다(`ScrollUnit="Item"`).<br /><br /> 누군가 `VirtualizingStackPanel.MakeVisible(v)`을 호출하여 요소 `v`를 보기로 스크롤합니다. 이것은 명시적으로 또는 암시적인 몇 가지 방법으로 실행될 수 있습니다. 아마도 가장 일반적인 방법은 간단히 `v`를 클릭하여 키보드 포커스를 부여하는 것입니다.<br /><br /> `v`에서 VirtualizingStackPanel까지의 시각적 부모 체인은 TreeViewItem을 통과합니다.<br /><br /> 즉, 이것은 TreeViewItem이 TreeView 외부에서 사용되고 사용자가 TreeViewItem의 하위 항목을 클릭하여 보기로 가져올 때 보입니다. TreeViewItem에 포커스 가능한 하위 항목이 없는 경우 이 문제는 발생하지 않습니다. 이것이 적중되는 상황의 예는 TreeViewItem이 DateTemplate의 루트일 때입니다.  이 문제가 적중하면 WPF 프레임워크 내에 InvalidCastException가 발생합니다.|  
|제안 해결 방법|이것을 위해 사용 가능한 핫픽스가 생성됩니다.|  
|범위|사소함|  
|버전|4.5|  
|형식|런타임|  
|분석기|CD0141|  
  
<a name="diagnostic143"></a>   
## <a name="143-x509certificateclaimsetfindclaims-considers-all-claimtypes"></a>143: X509CertificateClaimSet.FindClaims가 모든 claimTypes를 고려합니다  
  
|||  
|-|-|  
|세부 정보|.NET Framework 4.6.1을 대상으로 하는 앱에서 X509 클레임 집합이 해당 SAN 필드에 여러 DNS 항목이 있는 인증서로부터 초기화되는 경우 FindClaims 메서드가 claimType 인수를 모든 DNS 항목과 일치시키려고 합니다.<br /><br /> 이전 버전의 .NET Framework를 대상으로 하는 앱의 경우에는 FindClaims 메서드가 claimType 인수를 마지막 DNS 항목만 일치시키려고 합니다.|  
|제안 해결 방법|이 변경은 .NET Framework 4.6.1을 대상으로 하는 응용 프로그램에만 영향을 줍니다. 이 변경 내용은 [DisableMultipleDNSEntries](https://msdn.microsoft.com/library/mt620030%28v=vs.110%29.aspx) 호환성 스위치로 비활성화(또는 4.6.1 전 버전을 대상으로 하는 경우 활성화)될 수 있습니다.|  
|범위|사소함|  
|버전|4.6.1|  
|형식|대상 변경|  
|영향을 받는 API|<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%28System.String%2CSystem.String%29?displayProperty=fullName>|  
|분석기|CD0143|  
  
<a name="diagnostic144"></a>   
## <a name="144-applicationfiltermessage-no-longer-throws-for-re-entrant-implementations-of-imessagefilterprefiltermessage"></a>144: Application.FilterMessage는 IMessageFilter.PreFilterMessage의 재진입 구현에 대해 더 이상 throw하지 않습니다  
  
|||  
|-|-|  
|설명|.NET Framework 4.6.1 전에는 AddMessageFilter 또는 RemoveMessageFilter를 호출하는(Application.DoEvents도 호출하는 동안) IMessageFilter.PreFilterMessage를 사용하여 Application.FilterMessage를 호출하면 IndexOutOfRangeException이 발생했습니다.<br /><br /> 4.6.1.NET Framework를 대상으로 하는 응용 프로그램부터 이 예외는 더 이상 throw되지 않으며 위에서 설명한 것처럼 재진입 필터가 사용될 수 있습니다.|  
|제안 해결 방법|위에서 설명한 것처럼 Application.FilterMessage가 재진입 IMessageFilter.PreFilterMessage 동작을 더 이상 throw하지 않습니다. 이것은 .NET Framework 4.6.1을 대상으로 하는 응용 프로그램에만 영향을 줍니다.<br /><br /> .NET Framework 4.6.1을 대상으로 하는 응용 프로그램은 [DontSupportReentrantFilterMessage](https://msdn.microsoft.com/library/mt620032%28v=vs.110%29.aspx) 호환성 스위치를 사용하여 이 변경을 옵트아웃(또는 이전 프레임워크를 대상으로 하는 응용 프로그램은 옵트인)할 수 있습니다.|  
|범위|Microsoft Edge|  
|버전|4.6.1|  
|형식|대상 변경|  
|영향을 받는 API|<xref:System.Windows.Forms.Application.FilterMessage%28System.Windows.Forms.Message%40%29?displayProperty=fullName>|  
|분석기|CD0144|  
  
<a name="diagnostic145"></a>   
## <a name="145-currentculture-is-not-preserved-across-wpf-dispatcher-operations"></a>145: CurrentCulture는 WPF 발송자 작업 간에 유지되지 않습니다.  
  
|||  
|-|-|  
|설명|.NET Framework 4.6부터, [발송자](https://msdn.microsoft.com/library/system.windows.threading.dispatcher%28v=vs.110%29.aspx) 내에서 생성된 CurrentCulture 또는 CurrentUICulture에 대한 변경 내용은 해당 발송자 작업이 끝날 때 손실됩니다. 마찬가지로, 발송자 작업 외부에서 생성된 CurrentCulture 또는 CurrentUICulture에 대한 변경 내용은 작업이 실행될 때 반영되지 않을 수 있습니다.<br /><br /> 즉, CurrentCulture 및 CurrentUICulture 변경 내용이 WPF UI 콜백과 WPF 응용 프로그램의 다른 코드 사이에서 흐르지 않을 수 있다는 것입니다.<br /><br /> .NET Framework 4.6을 대상으로 하는 응용 프로그램부터 [ExecutionContext](https://msdn.microsoft.com/library/system.threading.executioncontext%28v=vs.110%29.aspx)에서의 변경으로 인해 CurrentCulture 및 CurrentUICulture가 실행 컨텍스트에 저장됩니다. WPF 발송자 작업이 작업을 시작할 때 사용된 실행 컨텍스트를 저장하고 작업이 완료되면 이전의 컨텍스트를 복원합니다. CurrentCulture 및 CurrentUICulture가 이제 해당 컨텍스트의 일부이므로 발송자 작업 내에서의 변경 내용이 작업 외부에서 유지되지 않습니다.|  
|제안 해결 방법|이 변경으로 인해 영향을 받은 응용 프로그램은 원하는 CurrentCulture 또는 CurrentUICulture를 필드에 저장하고 CurrentCulture 및 CurrentUICulture가 설정되도록 수정한 모든 발송자 작업 본문(UI 이벤트 콜백 처리기 포함)을 확인하여 해결할 수 있습니다. 또는 WPF 변경 내부의 ExecutionContext 변경이 .NET Framework 4.6 이상을 대상으로 하는 앱에만 영향을 주기 때문에 이 중단은 .NET Framework 4.5.2를 대상으로 하여 방지할 수 있습니다.|  
|범위|사소함|  
|버전|4.6|  
|형식|대상 변경|  
|분석기|CD0145|
