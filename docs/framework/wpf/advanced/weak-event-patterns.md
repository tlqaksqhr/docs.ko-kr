---
title: "약한 이벤트 패턴"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3f024ae77740c596d8646b10a036428e2342d084
ms.sourcegitcommit: 8ed4ebc15b5ef89d06a7507dc9d5e306e30accf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2017
---
# <a name="weak-event-patterns"></a>약한 이벤트 패턴
응용 프로그램에서 있기 이벤트 소스에 연결 된 처리기를 조정 하 여 처리기는 소스에 연결 하는 수신기 개체 소멸 되지 것입니다. 이 경우 메모리 누수가 발생할 수 있습니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]특정 이벤트에 대 한 전용된 관리자 클래스를 제공 하 고 해당 이벤트에 대 한 수신기에 인터페이스를 구현 하 여이 문제를 해결 하는 데 사용할 수 있는 디자인 패턴을 소개 합니다. 이 디자인 패턴 이라고는 *취약 한 이벤트 패턴*합니다.  
  
## <a name="why-implement-the-weak-event-pattern"></a>취약 한 이벤트 패턴을 구현 하는 이유  
 이벤트를 수신 대기 메모리 누수 될 수 있습니다. 이벤트를 수신 하는 일반적인 방법 처리기 이벤트 소스에 연결 하는 언어 관련 구문을 사용 하는 것입니다. 예를 들어 [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)], 구문이 않은: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`합니다.  
  
 이 기술은 이벤트 소스에서 이벤트 수신기에 강력한 참조를 만듭니다. 일반적으로 수신기에 대 한 이벤트 처리기를 연결 하면 해당 수신기는 영향을 원본 개체 수명 (이벤트 처리기가 명시적으로 제거) 하는 개체 수명이 합니다. 하지만 속해 있는지 여부 현재 소스의 수명이 아니라에 응용 프로그램의 시각적 트리 같은 개체 수명에 대 한 다른 요인에 의해 제어 수신기의 하려는 특정 상황에서는 있습니다. 메모리 누수 일반 이벤트 패턴으로 인해 소스 개체 수명 수신기의 개체 수명을 넘어가는, 때마다: 수신기 예정 보다 더 이상 활성 상태로 유지 됩니다.  
  
 취약 한 이벤트 패턴이 메모리 누수 문제를 해결 하기 위해 설계 되었습니다. 수신기는 이벤트에 대 한 등록 해야 하지만 수신기 명시적으로 알지 못하는 등록을 취소 하는 경우 때마다 취약 한 이벤트 패턴을 사용할 수 있습니다. 소스 개체 수명 수신기의 적절 한 개체 수명 초과할 때마다 취약 한 이벤트 패턴을 사용할 수도 있습니다. (이 경우 *유용한* 사용자에 의해 결정 됩니다.) 취약 한 이벤트 패턴에는 수신기를 대 한 등록 한 어떤 방식으로든에서 수신기의 개체 수명 특성을 영향을 주지 않고 이벤트를 받을 수 있습니다. 실제로, 소스에서 대 한 암시적된 참조가 수신기가 가비지 수집을 수행할 수 있는지을 확인 하지 않습니다. 참조는 따라서 이름은 취약 한 이벤트 패턴 및 관련 된 약한 참조를 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]합니다. 수신기는 가비지 수집 하거나 그렇지 않으면 제거 될 수 있습니다 및 소스 삭제 된 개체에 대 한 존재할 처리기 참조를 보존 하지 않고 계속할 수 있습니다.  
  
## <a name="who-should-implement-the-weak-event-pattern"></a>취약 한 이벤트 패턴을 구현 해야가?  
 취약 한 이벤트 패턴을 구현할 컨트롤 작성자에 주로 흥미로운 부분입니다. 컨트롤 작성자는 동작과 컨트롤 및 삽입 되는 응용 프로그램에 아무런 영향 제약 주로 담당 하 합니다. 여기에 컨트롤 개체 수명 동작 특히 설명한 메모리 누수 문제를 처리 합니다.  
  
 특정 시나리오를 기본적으로 취약 한 이벤트 패턴의 응용 프로그램에 활용 합니다. 이러한 시나리오 중 하나에 데이터 바인딩입니다. 이 데이터 바인딩에서 바인딩 대상 수신기 개체에 완전히 독립적인 소스 개체에 대 한 일반적입니다. 많은 부분이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 취약 한 이벤트 패턴의 이벤트 구현 방식에 적용 한 데이터 바인딩이 이미 있습니다.  
  
## <a name="how-to-implement-the-weak-event-pattern"></a>취약 한 이벤트 패턴을 구현 하는 방법  
 취약 한 이벤트 패턴을 구현 하는 방법은 세 가지가 있습니다. 다음 표에서 세 가지 방법을 고 각 사용 시기에 대 한 몇 가지 지침을 제공 합니다.  
  
|방법|구현 시기|  
|--------------|-----------------------|  
|기존 취약 한 이벤트 관리자 클래스를 사용 하 여|구독 하려는 이벤트에 해당 하는 경우 <xref:System.Windows.WeakEventManager>, 기존 취약 한 이벤트 관리자를 사용 합니다. WPF와 함께 제공 되는 취약 한 이벤트 관리자의 목록에 대 한 참조의 상속 계층 구조는 <xref:System.Windows.WeakEventManager> 클래스입니다. 그러나 Note, 되므로 다른 인증 방법 중 하나를 선택 해야 것 WPF와 함께 제공 되는 비교적 취약 한 이벤트 관리자가 없음을 합니다.|  
|일반 약한 이벤트 관리자 클래스를 사용 하 여|일반을 사용 하 여 <xref:System.Windows.WeakEventManager%602> 기존 <xref:System.Windows.WeakEventManager> 을 사용할 수 없는 쉽게를 구현 하는 방법을 원하고 없는 우려 효율성에 대 한 합니다. 제네릭 <xref:System.Windows.WeakEventManager%602> 에서 기존 또는 사용자 지정 취약 한 이벤트 관리자 보다 덜 효율적입니다. 예를 들어 제네릭 클래스는 이벤트의 이름이 지정 된 이벤트를 검색 하기 위해 더 많은 리플렉션을 수행 합니다. 또한 제네릭을 사용 하 여 이벤트를 등록 하려면 코드 <xref:System.Windows.WeakEventManager%602> 더 기존를 사용 하 여 보다 자세한 정보 또는 사용자 지정은 <xref:System.Windows.WeakEventManager>합니다.|  
|취약 한 사용자 지정 이벤트 관리자 클래스 만들기|사용자 지정 만들기 <xref:System.Windows.WeakEventManager> 기존 <xref:System.Windows.WeakEventManager> 사용할 수 없으면 효율성을 극대화 하 고 있습니다. 사용자 지정을 사용 하 여 <xref:System.Windows.WeakEventManager> 구독할 이벤트는 더 효율적 이지만 시작 부분에 더 많은 코드 작성의 비용 발생 시 키 지 않습니다.|  
  
 다음 섹션에는 취약 한 이벤트 패턴을 구현 하는 방법을 설명 합니다.  이 논의의 목적에 대 한 이벤트를 구독할 다음과 같은 특징이 있습니다.  
  
-   이벤트 이름이 잘못 된 `SomeEvent`합니다.  
  
-   이벤트에 의해 발생 되는 `EventSource` 클래스입니다.  
  
-   이벤트 처리기에 형식이: `SomeEventEventHandler` (또는 `EventHandler<SomeEventEventArgs>`).  
  
-   이 이벤트는 형식의 매개 변수 전달 `SomeEventEventArgs` 이벤트 처리기에 있습니다.  
  
### <a name="using-an-existing-weak-event-manager-class"></a>기존 약한 이벤트 관리자 클래스를 사용 하 여  
  
1.  관리자를 기존 약한 이벤트를 찾습니다.  
  
     WPF와 함께 제공 되는 취약 한 이벤트 관리자의 목록에 대 한 참조의 상속 계층 구조는 <xref:System.Windows.WeakEventManager> 클래스입니다.  
  
2.  일반 이벤트 후크 하는 대신 새로운 취약 한 이벤트 관리자를 사용 합니다.  
  
     예를 들어, 코드 패턴을 사용 하 여 이벤트를 구독할 경우:  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     다음 패턴으로 변경 합니다.  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     마찬가지로, 사용자 코드는 다음 패턴을 사용 하 여 이벤트를 등록 취소 하는 경우:  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     다음 패턴으로 변경 합니다.  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a>제네릭 약한 이벤트 관리자 클래스를 사용 하 여  
  
1.  제네릭을 사용 하 여 <xref:System.Windows.WeakEventManager%602> 일반 이벤트 후크 대신 클래스입니다.  
  
     사용 하는 경우 <xref:System.Windows.WeakEventManager%602> 이벤트 원본이 이벤트 수신기를 등록 하려면 제공 및 <xref:System.EventArgs> 형식이 형식 매개 변수는 클래스와 호출 <xref:System.Windows.WeakEventManager%602.AddHandler%2A> 다음 코드에 나와 있는 것 처럼:  
  
    ```  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a>사용자 지정 약한 이벤트 관리자 클래스 만들기  
  
1.  다음 클래스 템플릿을 프로젝트에 복사 합니다.  
  
     이 클래스에서 상속 된 <xref:System.Windows.WeakEventManager> 클래스입니다.  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2.  대체는 `SomeEventWeakEventManager` 사용자 이름으로 이름입니다.  
  
3.  이벤트에는 해당 이름의 앞에서 설명한 세 가지 이름을 바꿉니다. (`SomeEvent`, `EventSource`, 및 `SomeEventEventArgs`)  
  
4.  관리 하는 이벤트로 동일한 표시 취약 한 이벤트 관리자 클래스의 표시 유형 (public / private, 내부)를 설정 합니다.  
  
5.  일반 이벤트 후크 하는 대신 새로운 취약 한 이벤트 관리자를 사용 합니다.  
  
     예를 들어, 코드 패턴을 사용 하 여 이벤트를 구독할 경우:  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     다음 패턴으로 변경 합니다.  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     마찬가지로, 사용자 코드는 다음 패턴을 사용 하 여 이벤트를 등록 취소 하는 경우:  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     다음 패턴으로 변경 합니다.  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.WeakEventManager>  
 <xref:System.Windows.IWeakEventListener>  
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)
