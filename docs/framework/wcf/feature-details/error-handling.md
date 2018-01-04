---
title: "오류 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c948841a-7db9-40ae-9b78-587d216cbcaf
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 29ae7505f3fcd460abe9e65974f564a296723aa1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="error-handling"></a>오류 처리
## <a name="error-handling-in-windows-communication-foundation"></a>Windows Communication Foundation의 오류 처리  
 서비스에서 예기치 않은 예외나 오류가 발생할 경우 여러 가지 방법으로 예외 처리 솔루션을 디자인할 수 있습니다. 단일 "올바른" 또는 "모범 사례" 없습니다 오류 처리 솔루션을 고려해 야 할 하나에 대 한 유효한 경로가 여러 개 있으면 합니다. 일반적으로 것의 처리 되지 않은 특성 및 WCF 구현을, 유형 및 빈도의 예외는 처리의 복잡성에 따라 아래 목록에서 다양 한 접근 방식이 결합 하는 하이브리드 솔루션을 구현 하는 하나는 예외 및 연관 된 모든 추적, 로깅 또는 정책 요구 사항입니다.  
  
 이 단원의 나머지 부분에서는 이러한 솔루션에 대해 자세히 설명합니다.  
  
### <a name="the-microsoft-enterprise-library"></a>Microsoft Enterprise Library  
 Microsoft Enterprise Library 예외 처리 응용 프로그램 블록을 사용하면 일반적인 디자인 패턴을 쉽게 구현할 수 있으며 엔터프라이즈 응용 프로그램의 모든 아키텍처 계층에서 발생하는 예외 처리를 위한 일관된 전략을 개발할 수 있습니다. Microsoft Enterprise Library 예외 처리 응용 프로그램 블록은 응용 프로그램 구성 요소의 catch 문에 포함된 일반적인 코드를 지원하도록 디자인되었습니다. 응용 프로그램 전체의 동일한 여러 catch 블록에서 이러한 코드(예: 예외 정보를 기록하는 코드)를 반복하는 대신 개발자는 예외 처리 응용 프로그램 블록을 사용하여 이 논리를 재사용 가능한 예외 처리기로 캡슐화할 수 있습니다.  
  
 이 라이브러리에는 기본 제공 오류 계약 예외 처리기가 포함되어 있습니다. 이 예외 처리기는 WCF(Windows® Communication Foundation) 서비스 경계에서 사용하도록 디자인되었으며 예외에서 새 오류 계약을 생성합니다.  
  
 응용 프로그램 블록은 일반적으로 사용되는 모범 사례를 통합하여 응용 프로그램 전반의 오류 처리를 위한 공통된 접근 방식을 제공하는 데 목적이 있습니다. 반면 직접 개발한 사용자 지정 오류 처리기 및 오류 계약이 유용한 경우도 있습니다. 예를 들어, 사용자 지정 오류 처리기는 자동으로 FaultExceptions에 대 한 모든 예외를 승격 하 고 응용 프로그램에 로깅 기능을 추가할 수 있는 좋은 기회를 제공 합니다.  
  
 자세한 내용은 참조 하십시오 [Microsoft Enterprise Library](http://msdn.microsoft.com/library/ff632023.aspx)합니다.  
  
### <a name="dealing-with-expected-exceptions"></a>예상한 예외 처리  
 모든 작업 또는 관련 확장성 지점에 예상 되는 예외를 catch 하 고,에서 복구할 수 있습니다 및 FaultException의 적절 한 사용자 지정 오류를 반환 여부를 결정 하는 적절 한 조치 과정\<T >  
  
### <a name="dealing-with-unexpected-exceptions-using-an-ierrorhandler"></a>IErrorHandler를 사용하여 예기치 않은 예외 처리  
 예기치 않은 예외를 처리 하려면 IErrorHandler를 "후크" 것 권장된 작업 과정입니다. 오류 처리기는 채널 계층, 아닌 WCF 런타임 수준 ("서비스 모델" 계층) 에서만 예외를 catch 합니다. 채널 수준에서 IErrorHandler를 후크하려면 사용자 지정 채널을 만드는 방법밖에 없지만 대부분의 시나리오에서 권장되지 않습니다.  
  
 "예기치 않은 예외"는 일반적으로 복구할 수 없는 예외 나 처리 예외가; 대신,이 예기치 않은 사용자 예외가 있습니다. 복구할 수 없는 예외 (예: 메모리 부족 예외)를 하나 일반적으로에서 처리는 [서비스 모델 예외 처리기](http://msdn.microsoft.com/library/system.servicemodel.dispatcher.exceptionhandler.aspx) 자동으로 – 일반적으로 처리할 수 없는 제대로 및 이러한 예외를 처리 하는 유일한 이유 전혀 추가 로깅을 수행 될 수 있습니다 또는 클라이언트에 표준 예외를 반환 합니다. 처리 예외는 메시지 처리 중 serialization, 인코더 또는 포맷터 수준에서 발생하며 일반적으로 IErrorHandler로는 처리될 수 없습니다. 이는 예외 발생 시점에 오류 처리기가 개입하기에는 너무 이르거나 늦기 때문입니다. 마찬가지로 전송 예외도 IErrorHandler로 처리될 수 없습니다.  
  
 IErrorHandler를 사용하면 예외가 throw될 때의 응용 프로그램 동작을 명시적으로 제어할 수 있습니다. 다음 작업을 수행할 수 있습니다.  
  
1.  클라이언트에 오류를 보낼지 여부를 결정합니다.  
  
2.  예외를 오류로 바꿉니다.  
  
3.  오류를 다른 오류로 바꿉니다.  
  
4.  로깅 또는 추적을 수행합니다.  
  
5.  다른 사용자 지정 작업을 수행합니다.  
  
 사용자 지정 오류 처리기를 서비스 채널 디스패처의 ErrorHandlers 속성에 추가하여 오류 처리기를 설치할 수 있습니다.  오류 처리기를 둘 이상 설치할 수 있으며 오류 처리기는 오류 처리기 컬렉션에 추가된 순서대로 호출됩니다.  
  
 IErrorHandler.ProvideFault는 클라이언트로 전송되는 오류 메시지를 제어합니다. 이 메서드는 서비스 작업에서 throw된 예외 유형에 관계없이 호출됩니다. 위의 작업 중 아무 것도 수행하지 않은 경우 WCF는 사용자 지정 오류 처리기가 없는 것으로 가정하고 IErrorHandler의 기본 동작을 사용합니다.  
  
 예외를 클라이언트로 보내기 전에 예외를 오류로 변환하기 위한 중앙 위치를 만들려는 경우(이 경우 인스턴스가 삭제되지 않으며 채널이 Faulted 상태로 전환되지 않음) 이 접근 방식을 사용해볼 수 있습니다.  
  
 IErrorHandler.HandleError 메서드는 일반적으로 오류 로깅, 시스템 알림, 응용 프로그램 종료 등의 오류 관련 동작을 구현하는 데 사용합니다. IErrorHandler.HandleError는 서비스 내의 여러 위치에서 호출될 수 있습니다. 또한 오류가 throw된 위치에 따라 작업과 동일한 스레드에서 HandleError 메서드를 호출할 수도 있고 그렇지 않을 수도 있지만 호출 여부에 대한 보장은 없습니다.  
  
### <a name="dealing-with-exceptions-outside-wcf"></a>WCF 외부의 예외 처리  
 대개 구성 예외, 데이터베이스 연결 문자열 예외 및 기타 유사한 예외는 WCF 응용 프로그램의 컨텍스트 내에서 발생하지만 서비스 모델이나 웹 서비스 자체로 인해 발생하는 예외는 아닙니다. 이러한 예외는 "일반" 예외 웹 서비스 외부와 동일 하 게 환경의 다른 외부 예외 처리를 처리 합니다.  
  
### <a name="tracing-exceptions"></a>예외 추적  
 추적은 모든 예외를 잠재적으로 볼 수 하나만 "범용" 현재 위치입니다. 예외 추적 및 로깅에 대한 자세한 내용은 "추적 및 로깅"을 참조하세요.  
  
### <a name="uri-template-errors-when-using-webgetattribute-and-webinvokeattribute"></a>WebGetAttribute 및 WebInvokeAttribute를 사용할 때의 UI 템플릿 오류  
 WebGet 및 WebInvoke 특성을 사용하면 요청 주소의 구성 요소를 작업 매개 변수에 매핑하는 URI 템플릿을 지정할 수 있습니다. 예를 들어 URI 템플릿 "weather/{state}/{city}"는 요청 주소를 리터럴 토큰, 매개 변수에 지정된 시/도, 매개 변수에 지정된 구/군/시에 매핑합니다. 그런 다음 이러한 매개 변수는 작업의 일부 형식 매개 변수에 이름으로 바인딩됩니다.  
  
 템플릿 매개 변수는 URI에 문자열 형식으로 표시되지만 형식화된 계약의 형식 매개 변수는 문자열이 아닌 다른 형식으로 표시될 수 있습니다. 따라서 작업을 호출하기 전에 변환이 수행되어야 합니다. A [변환 형식 표](http://msdn.microsoft.com/library/bb412172.aspx) 를 사용할 수 있습니다.  
  
 그러나 변환이 실패할 경우 문제가 있다는 사실을 작업에 알릴 방법이 없습니다. 이 경우 디스패치 오류 형태로 형식 변환 오류가 표출됩니다.  
  
 오류 처리기를 설치하여 다른 디스패치 오류 유형과 동일한 방법으로 형식 변환 디스패치 오류를 검사할 수 있습니다. 서비스 수준 예외를 처리하기 위해 IErrorHandler 확장성 지점이 호출됩니다. 이때 호출자에게 전송될 응답을 선택하고 사용자 지정 작업 및 보고를 수행할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [기본 WCF 오류 처리](http://msdn.microsoft.com/library/gg281715.aspx)
