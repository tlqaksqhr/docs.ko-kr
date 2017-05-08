---
title: "응용 프로그램 추적 및 조율 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "추적[.NET Framework]"
  - "디버깅 [.NET Framework], 계측"
  - "성능 모니터링, 계측"
  - "계측에 대 한 계측"
  - "추적에 대 한 추적 [.NET Framework]"
  - "성능 모니터링, 코드 추적"
  - "Trace 클래스,.NET 응용 프로그램 계측"
ms.assetid: 773b6fc4-9013-4322-b728-5dec7a72e743
caps.latest.revision: 21
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 21
---
# 응용 프로그램 추적 및 조율
추적은 실행되는 동안 응용 프로그램의 실행을 모니터링할 수 있는 방법입니다. 개발할 때 .NET Framework 응용 프로그램에 추적 및 디버깅 계측을 추가할 수 있으며, 응용 프로그램을 개발하는 동안 및 배포한 후에 해당 계측을 모두 사용할 수 있습니다. 사용할 수는 <xref:System.Diagnostics.Trace?displayProperty=fullName>, <xref:System.Diagnostics.Debug?displayProperty=fullName>, 및 <xref:System.Diagnostics.TraceSource?displayProperty=fullName> 오류 및 응용 프로그램 실행 로그, 텍스트 파일 또는 나중에 분석에 대 한 다른 장치에 대 한 정보를 기록 하는 클래스입니다.  
  
 용어 *계측* 제품의 성능 수준을 모니터링 하거나 측정 하 고 오류를 진단 하는 능력을 나타냅니다. 프로그래밍에서 이 용어는 다음을 통합하는 응용 프로그램 기능을 의미합니다.  
  
-   **코드 추적** -런타임에 응용 프로그램의 실행에 대 한 정보 메시지를 받습니다.  
  
-   **디버깅** -를 추적 하 고 개발 중인 응용 프로그램에서 프로그래밍 오류를 수정 합니다. 자세한 내용은 참조 [디버깅](../Topic/Debugging%20in%20Visual%20Studio.md)합니다.  
  
-   **성능 카운터** -응용 프로그램의 성능을 추적할 수 있도록 하는 구성 요소입니다. 자세한 내용은 참조 [성능 카운터](../../../docs/framework/debug-trace-profile/performance-counters.md)합니다.  
  
-   **이벤트 로그** -수 있는 구성 요소가 수신 하 고 응용 프로그램의 실행에서 주요 이벤트를 추적 합니다. 자세한 내용은 참조는 <xref:System.Diagnostics.EventLog> 클래스입니다.  
  
 분산 응용 프로그램에서는 코드의 전략적 위치에 trace 문을 배치하여 응용 프로그램을 계측하는 것이 특히 유용합니다. trace 문을 통해 응용 프로그램을 계측하여 문제가 발생할 때 정보를 표시하는 것은 물론 응용 프로그램의 성능을 모니터링할 수 있습니다.  
  
 <xref:System.Diagnostics.TraceSource> 클래스는 향상 된 추적 기능 및 이전의 정적 메서드 대신 사용할 수 있습니다 제공 <xref:System.Diagnostics.Trace> 및 <xref:System.Diagnostics.Debug> 추적 클래스입니다. 친숙 한 <xref:System.Diagnostics.Trace> 및 <xref:System.Diagnostics.Debug> 클래스가 여전히 널리 사용 되지만 <xref:System.Diagnostics.TraceSource> 클래스와 같은 새 추적 명령에 권장 됩니다 <xref:System.Diagnostics.TraceSource.TraceEvent%2A> 및 <xref:System.Diagnostics.TraceSource.TraceData%2A>합니다.  
  
 <xref:System.Diagnostics.Trace> 및 <xref:System.Diagnostics.Debug> 클래스는 그의 프로시저와 함수를 제외 하 고 동일는 <xref:System.Diagnostics.Trace> 으로 릴리스 빌드로 클래스는 기본적으로 컴파일됩니다는 <xref:System.Diagnostics.Debug> 는 그렇지 않습니다.  
  
 <xref:System.Diagnostics.Trace> 및 <xref:System.Diagnostics.Debug> 클래스 모니터링 하 고 개발 중 이나 배포 후 응용 프로그램 성능을 조사할 수단을 제공 합니다. 예를 들어, 사용할 수는 <xref:System.Diagnostics.Trace> 있으므로 응용 프로그램의 효율성을 모니터링할 수 있습니다 (예: 새 데이터베이스 연결 만들기)이 발생할 때 특정 유형의 배포 응용 프로그램에서 작업을 추적 하는 클래스입니다.  
  
## <a name="code-tracing-and-debugging"></a>코드 추적 및 디버깅  
 개발 과정의 출력 메서드를 사용할 수는 <xref:System.Diagnostics.Debug> Visual Studio 통합된 개발 환경 (IDE)의 출력 창에 메시지를 표시 하는 클래스입니다. 예를 들면 다음과 같습니다.  
  
```vb  
Trace.WriteLine("Hello World!")  
Debug.WriteLine("Hello World!")  
  
```  
  
```csharp  
System.Diagnostics.Trace.WriteLine("Hello World!");  
System.Diagnostics.Debug.WriteLine("Hello World!");  
  
```  
  
 이러한 예의 각 "Hello World!"에 표시 됩니다. 출력 창에서 디버거는 응용 프로그램을 실행할 때.  
  
 이 경우 응용 프로그램을 디버그하고 테스트 환경에서의 해당 동작에 따라 성능을 최적화할 수 있습니다. 와 디버그 빌드에서 응용 프로그램을 디버깅할 수는 <xref:System.Diagnostics.Debug> 조건부 특성이 모든 디버깅 출력을 받을 수 있도록 설정 합니다. 응용 프로그램을 릴리스할 준비가 되 면을 설정 하지 않고 릴리스 빌드를 컴파일할 수는 <xref:System.Diagnostics.Debug> 조건부 특성을 하므로 컴파일러가 디버깅 코드를 최종 실행 파일에 포함 되지 것입니다. 자세한 내용은 참조 [하는 방법: 추적 및 디버그를 사용한 조건부 컴파일](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)합니다. 응용 프로그램에 대 한 다양 한 빌드 구성에 대 한 자세한 내용은 참조 하십시오. [컴파일 및 빌드](../Topic/Compiling%20and%20Building%20in%20Visual%20Studio.md)합니다.  
  
 또한의 메서드를 사용 하 여 설치 된 응용 프로그램에서 코드 실행 추적할 수 있습니다는 <xref:System.Diagnostics.Trace> 클래스입니다. 배치 하 여 [추적 스위치](../../../docs/framework/debug-trace-profile/trace-switches.md) 코드에서 추적 발생 여부와 어떻게 광범위 하 게 제어할 수 있습니다. 이 경우 프로덕션 환경에서 응용 프로그램의 상태를 모니터링할 수 있습니다. 이 기능은 여러 컴퓨터에서 실행되는 여러 구성 요소를 사용하는 비즈니스 응용 프로그램에서 특히 중요합니다. 배포 후 구성 파일을 통해 스위치를 사용하는 방법을 제어할 수 있습니다. 자세한 내용은 참조 [하는 방법: 만들기, 초기화 및 추적 스위치 구성](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)합니다.  
  
 추적을 사용하려는 응용 프로그램을 개발하는 경우 일반적으로 추적 및 디버깅 메시지 둘 다를 응용 프로그램 코드에 포함합니다. 설정 하지 않고 릴리스 빌드를 컴파일할 수 응용 프로그램을 배포할 준비가 된 **디버그** 조건부 특성입니다. 그러나 켤 수 있습니다는 **추적** 조건부 특성 컴파일러는 실행 파일에 추적 코드를 포함 되도록 합니다. 자세한 내용은 참조 [하는 방법: 추적 및 디버그를 사용한 조건부 컴파일](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)합니다.  
  
### <a name="phases-of-code-tracing"></a>코드 추적 단계  
 코드 추적에는 다음 세 단계가 있습니다.  
  
1.  **계측** -응용 프로그램에 추적 코드를 추가 합니다.  
  
2.  **추적** -추적 코드가 지정된 된 대상에 정보를 씁니다.  
  
3.  **분석** — 식별 하 고 응용 프로그램의 문제를 파악 추적 정보를 확인 합니다.  
  
 개발 중에 모든 디버그 및 추적 출력 메서드는 기본적으로 Visual Studio의 출력 창에 정보를 씁니다. 배포된 응용 프로그램에서 메서드는 지정된 대상에 추적 정보를 씁니다. 추적 또는 디버깅의 출력 대상을 지정에 대 한 자세한 내용은 참조 하십시오. [추적 수신기](../../../docs/framework/debug-trace-profile/trace-listeners.md)합니다.  
  
 다음은 추적을 사용하여 배포 된 응용 프로그램의 잠재적 문제를 분석 및 해결하는 작업과 일반적으로 관련된 주요 단계를 전체적으로 보여 줍니다. 이러한 단계를 수행하는 방법에 대한 자세한 내용은 해당 링크를 참조하세요.  
  
##### <a name="to-use-tracing-in-an-application"></a>응용 프로그램에서 추적을 사용하려면  
  
1.  응용 프로그램을 배포한 후 온사이트에서 수신할 추적 출력을 고려합니다.  
  
2.  스위치 집합을 만듭니다. 자세한 내용은 참조 [하는 방법: 추적 스위치 구성](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)합니다.  
  
3.  응용 프로그램 코드에 trace 문을 추가합니다.  
  
4.  추적 출력을 표시할 위치를 결정하고 적절한 수신기를 추가합니다. 자세한 내용은 참조 [수신기 만들기 및 초기화 추적](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-listeners.md)합니다.  
  
5.  응용 프로그램 및 응용 프로그램에 포함된 추적 코드를 테스트 및 디버그합니다.  
  
6.  다음 절차 중 하나를 사용하여 응용 프로그램을 실행 코드로 컴파일합니다.  
  
    -   사용 하는 **빌드** 메뉴와 함께 **디버그** 의 페이지는 **속성 페이지** 대화 상자에 **솔루션 탐색기**합니다. 이 절차는 Visual Studio에서 컴파일할 때 사용합니다.  
  
         \- 또는 -  
  
    -   사용 된 **추적** 및 **디버그** 컴파일의 명령줄 메서드에 대 한 컴파일러 지시문입니다. 자세한 내용은 참조 [추적 및 디버그를 사용한 조건부 컴파일](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)합니다. 이 절차는 명령줄에서 컴파일할 때 사용합니다.  
  
7.  런타임 중에 문제가 발생하는 경우 적절한 추적 스위치를 설정합니다. 자세한 내용은 참조 [추적 스위치 구성](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)합니다.  
  
     추적 코드는 지정된 대상(예: 화면, 텍스트 파일 또는 이벤트 로그)에 추적 메시지를 씁니다. 에 포함 된 수신기의 형식에서 **Trace.Listeners** 컬렉션에 따라 대상이 결정 합니다.  
  
8.  추적 메시지를 분석하여 응용 프로그램의 문제를 식별하고 파악합니다.  
  
## <a name="trace-instrumentation-and-distributed-applications"></a>추적 계측 및 분산 응용 프로그램  
 분산 응용 프로그램을 만드는 경우 사용되는 방식으로 응용 프로그램을 테스트하기 어려울 수 있습니다. 운영 체제나 웹 브라우저의 가능한 모든 조합(모든 지역화된 언어 옵션 포함)을 테스트하거나 동시에 응용 프로그램에 액세스하는 다수의 사용자를 시뮬레이션할 수 있는 개발 팀은 거의 없습니다. 이러한 상황에서는 분산 응용 프로그램이 높은 볼륨, 다양한 설정 및 고유한 최종 사용자 동작에 응답하는 방식을 테스트할 수 없습니다. 또한 분산 응용 프로그램의 많은 부분에는 이러한 부분과 직접 상호 작용하거나 해당 활동을 볼 수 있는 사용자 인터페이스가 없습니다.  
  
 그러나 보완할 수 있습니다이 특히 내용 발생 한 문제와, 시스템 관리자에 게 특정 이벤트를 설명 하는 분산된 응용 프로그램을 사용 하 여 *계측* 응용 프로그램-즉, 코드의 전략적 위치에 추적 문을 배치 하 여 합니다. 그러면 런타임에 예기치 않은 문제가 발생할 경우(예: 과도하게 느린 응답 시간) 가능성이 높은 원인을 확인할 수 있습니다.  
  
 trace 문을 통해 원래 소스 코드를 검사, 수정 및 다시 컴파일하고 디버깅 환경 내에서 런타임 오류 생성을 시도하는 어려운 작업을 피할 수 있습니다. 응용 프로그램을 계측하여 오류를 표시하는 것은 물론 성능을 모니터링할 수도 있습니다.  
  
## <a name="strategic-placement-of-trace-statements"></a>Trace 문의 전략적 배치  
 런타임 중에 사용하기 위해 trace 문을 배치할 때는 특별히 주의해야 합니다. 가능한 모든 추적 시나리오가 적절하게 처리되도록 배포된 응용 프로그램에서 필요할 가능성이 큰 추적 정보를 고려해야 합니다. 그러나 추적을 사용하는 응용 프로그램은 매우 광범위하기 대문에 추적의 전략적 배치에 대한 일반적인 지침은 없습니다. Trace 문 배치에 대 한 자세한 내용은 참조 하십시오. [하는 방법: 응용 프로그램 코드에 Trace 문 추가](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)합니다.  
  
## <a name="output-from-tracing"></a>추적 출력  
 추적 출력은 라는 개체에 의해 수집 *수신기*합니다. 수신기는 추적 출력을 받아 출력 장치(일반적으로 창, 로그 또는 텍스트 파일)에 쓰는 개체입니다. 일반적으로에 추가 하는 추적 수신기가 만들어지면는 <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=fullName> 컬렉션, 모든 추적 출력을 받을 수 있습니다.  
  
 추적 정보는 항상 기록 최소한 기본 <xref:System.Diagnostics.Trace> 출력 대상에는 <xref:System.Diagnostics.DefaultTraceListener>합니다. 어떤 이유로 삭제 한 경우는 <xref:System.Diagnostics.DefaultTraceListener> 다른 수신기를 추가 하지 않고는 <xref:System.Diagnostics.Trace.Listeners%2A> 컬렉션, 추적 메시지를 받지 것입니다. 자세한 내용은 참조 [추적 수신기](../../../docs/framework/debug-trace-profile/trace-listeners.md)합니다.  
  
 6 개의 <xref:System.Diagnostics.Debug> 멤버 및 <xref:System.Diagnostics.Trace> 추적 정보를 기록 하는 메서드는 다음 표에 나열 됩니다.  
  
|메서드|출력|  
|------------|------------|  
|**어설션**|지정된 텍스트 또는 지정되지 않은 경우 호출 스택입니다. 만 출력이 기록에 대 한 인수로 지정 된 조건이 **Assert** 문이 **false**합니다.|  
|**실패**|지정된 텍스트 또는 지정되지 않은 경우 호출 스택입니다.|  
|**쓰기**|지정된 텍스트입니다.|  
|**WriteIf**|조건에 대 한 인수로 지정 된 경우 지정된 된 텍스트는 **WriteIf** 문을 충족 됩니다.|  
|**WriteLine**|지정된 텍스트와 캐리지 리턴입니다.|  
|**WriteLineIf**|조건에 대 한 인수로 지정 된 경우 지정된 된 텍스트와 캐리지 리턴는 **WriteLineIf** 문을 충족 됩니다.|  
  
 모든 수신기는 <xref:System.Diagnostics.Trace.Listeners%2A> 위 표에 설명 된 메시지를 수신 하는 컬렉션 하지만 메시지를 받는 수신기의 종류에 따라 다른 동작이 수행 될 수 있습니다. 예를 들어는 <xref:System.Diagnostics.DefaultTraceListener> 받을 경우 어설션 대화 상자를 표시 한 **실패** 했는지 아니면 실패 했는지 **Assert** 알림, 하지만 <xref:System.Diagnostics.TextWriterTraceListener> 출력을 해당 스트림에 씁니다.  
  
 고유한 수신기를 구현하여 사용자 지정 결과를 생성할 수 있습니다. 예를 들어 사용자 지정 추적 수신기는 메시지 상자에 메시지를 표시하거나 데이터베이스에 연결하여 테이블에 메시지를 추가할 수 있습니다. 모든 사용자 지정 수신기는 위에서 언급한&6;가지 메서드를 지원해야 합니다. 개발자 정의 수신기를 만드는 방법에 대 한 자세한 내용은 참조 하십시오. <xref:System.Diagnostics.TraceListener> .NET Framework 참조에서.  
  
> [!NOTE]
>  [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], **Debug.Write**, **Debug.WriteIf**, **Debug.WriteLine**, 및 **Debug.WriteLineIf** 메서드 바뀐는 **Debug.Print** 이전 버전의 Visual Basic에서 사용할 수 있었던 메서드.  
  
 **작성** 및 **WriteLine** 메서드 항상 텍스트를 씁니다 지정 해야 합니다. **Assert**, **WriteIf**, 및 **WriteLineIf** 지정된 된 텍스트를 작성 여부를 제어 하는 부울 인수를 필요로 하는 경우이 식은 지정된 된 텍스트 작성; **true** (에 대 한 **WriteIf** 및 **WriteLineIf**), 또는 **false** (에 대 한 **Assert**). **실패** 메서드는 항상 지정된 된 텍스트를 씁니다. 자세한 내용은 참조 [하는 방법: 응용 프로그램 코드에 Trace 문 추가](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md) 및.NET Framework 참조 합니다.  
  
## <a name="security-concerns"></a>보안 고려 사항  
 ASP.NET 응용 프로그램을 배포하기 전에 추적 및 디버깅을 사용하지 않도록 설정하지 않으면 응용 프로그램이 해당 정보를 노출하여 악성 프로그램에서 악용될 수 있습니다. 자세한 내용은 참조 [하는 방법: 추적 및 디버그를 사용한 조건부 컴파일](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md), [컴파일 및 빌드](../Topic/Compiling%20and%20Building%20in%20Visual%20Studio.md), 및 [하는 방법: 만들기, 초기화 및 추적 스위치 구성](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)합니다. IIS(인터넷 정보 서비스)를 통해 디버깅을 구성할 수도 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Diagnostics.Trace>   
 <xref:System.Diagnostics.TraceSource>   
 [코드 계약](../../../docs/framework/debug-trace-profile/code-contracts.md)   
 [C#, F # 및 Visual Basic 프로젝트 형식](../Topic/Debugging%20Preparation:%20C%23,%20F%23,%20and%20Visual%20Basic%20Project%20Types.md)   
 [방법: 응용 프로그램 코드에 추적 문 추가](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)   
 [방법: 추적 및 디버그를 사용한 조건부 컴파일](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)   
 [방법: 만들기, 초기화 및 추적 스위치 구성](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)   
 [방법: 추적 소스 생성 및 초기화](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-sources.md)   
 [방법: 추적 수신기와 함께 TraceSource 및 필터 사용](../../../docs/framework/debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners.md)   
 [추적 수신기](../../../docs/framework/debug-trace-profile/trace-listeners.md)   
 [추적 스위치](../../../docs/framework/debug-trace-profile/trace-switches.md)