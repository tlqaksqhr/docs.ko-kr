---
title: "약한 이벤트 패턴 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "이벤트 처리기, 약한 이벤트 패턴"
  - "IWeakEventListener 인터페이스"
  - "약한 이벤트 패턴 구현"
  - "WeakEventManager 클래스"
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# 약한 이벤트 패턴
응용 프로그램에서는 이벤트 소스에 연결된 처리기가 처리기를 소스에 연결한 수신기 개체와 함께 삭제되지 않을 수 있습니다.  이로 인해 메모리 누수가 발생할 수 있습니다.  [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에는 특정 이벤트에 전용 관리자 클래스를 제공하고 해당 이벤트의 수신기에 인터페이스를 구현함으로써 이러한 문제를 해결하는 데 사용할 수 있는 특수한 디자인 패턴이 도입되었습니다.  이 디자인 패턴을 *약한 이벤트 패턴*이라고 합니다.  
  
## 약한 이벤트 패턴을 구현하는 이유  
 이벤트 수신은 메모리 누수를 야기할 수 있습니다.  일반적으로 이벤트는 소스의 이벤트에 처리기를 연결하는 언어별 구문을 사용하여 수신합니다.  예를 들어 [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)]에서는 이 구문이 `source.SomeEvent += new SomeEventHandler(MyEventHandler)`입니다.  
  
 이 방법을 사용하면 이벤트 소스에서 이벤트 수신기로의 강력한 참조가 만들어집니다.  일반적으로 수신기에 대한 이벤트 처리기를 연결하면 해당 수신기의 개체 수명이 소스의 개체 수명의 영향을 받게 됩니다. 단, 이벤트 처리기를 명시적으로 제거한 경우에는 예외입니다.  하지만 소스의 수명이 아니라 수신기가 응용 프로그램의 시각적 트리에 현재 속해 있는지 여부와 같은 다른 요소를 기준으로 수신기의 개체 수명을 제어하려는 경우가 있습니다.  소스의 개체 수명이 수신기의 개체 수명보다 긴 경우 일반적인 이벤트 패턴으로 인해 메모리 누수가 발생합니다. 즉, 수신기가 의도했던 것보다 오래 활성 상태를 유지합니다.  
  
 약한 이벤트 패턴은 이러한 메모리 누수 문제를 해결할 수 있도록 디자인되었습니다.  약한 이벤트 패턴은 이벤트에 대해 수신기를 등록해야 하지만 수신기가 자신의 등록 취소 시기를 명시적으로 알지 못하는 경우에 사용할 수 있습니다.  또한 소스의 개체 수명이 수신기의 적절한 개체 수명보다 긴 경우에도 약한 이벤트 패턴을 사용할 수 있는데  이 경우 *적절한* 수명은 사용자에 의해 결정됩니다. 약한 이벤트 패턴을 사용하면 수신기의 개체 수명 특성에 영향을 주지 않고 수신기가 이벤트에 대해 등록하여 이벤트를 수신할 수 있습니다.  수신기를 가비지 수집할 수 있는지 여부를 결정할 때는 소스로부터의 암시적 참조가 실제로는 어떤 영향도 주지 않습니다.  이러한 참조를 약한 참조라고 합니다. 약한 이벤트 패턴 및 관련 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]도 이를 반영하여 이름이 지정되었습니다.  이 경우 수신기를 가비지 수집하거나 다른 방법을 통해 삭제할 수 있으며 소스는 삭제된 개체에 대한 수집할 수 없는 처리기 참조를 보유하지 않고도 계속 존재할 수 있습니다.  
  
## 약한 이벤트 패턴을 구현해야 하는 사용자  
 약한 이벤트 패턴 구현은 주로 컨트롤 작성자와 관련된 기능입니다.  컨트롤 작성자는 컨트롤의 동작과 제약, 컨트롤이 삽입된 응용 프로그램에 컨트롤이 미치는 영향을 주로 담당합니다.  여기에는 컨트롤의 개체 수명 동작과 앞에서 설명한 메모리 누수 문제에 대한 처리 등이 포함됩니다.  
  
 본질적으로 약한 이벤트 패턴의 적용에 중점을 두는 시나리오도 있습니다.  이러한 시나리오 중 하나가 데이터 바인딩입니다.  데이터 바인딩에서는 일반적으로 소스 개체가 바인딩의 대상인 수신기 개체와 완전히 독립적입니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 데이터 바인딩의 대부분의 측면에는 이벤트 구현 방법에 있어 약한 이벤트 패턴이 이미 적용되어 있습니다.  
  
## 약한 이벤트 패턴을 구현하는 방법  
 약한 이벤트 패턴을 구현 하는 방법은 다음 세 가지가 있습니다.  다음 표에 나열 된 세 가지 방법 및 사용 해야 합니다에 대 한 몇 가지 지침을 제공 합니다.  
  
|방법|구현 해야 하는 경우|  
|--------|-----------------|  
|기존 약한 이벤트 매니저 클래스를 사용 합니다.|해당 하는 이벤트를 구독할 수 있는 경우 <xref:System.Windows.WeakEventManager>, 기존 약한 이벤트 관리자를 사용 합니다.  상속 계층 구조에서 WPF에 포함 된 약한 이벤트 관리자 목록을 참조는 <xref:System.Windows.WeakEventManager> 클래스입니다.  그러나 다른 방법 중 하나를 선택 할 수 있도록 WPF에 포함 된 몇 가지 상대적으로 약한 이벤트 관리자는 note입니다.|  
|일반 약한 이벤트 매니저 클래스 사용|제네릭 사용 <xref:System.Windows.WeakEventManager%602> 기존에 때 <xref:System.Windows.WeakEventManager> 사용할 수 없습니다, 쉽게 구현 하 고 사용 중인 효율성에 대 한 관계가 있습니다.  일반 <xref:System.Windows.WeakEventManager%602> 는 기존 또는 사용자 지정 약한 이벤트 매니저 보다 효율적이 지 않습니다.  예를 들어, 제네릭 클래스 이벤트의 이름이 지정 된 이벤트를 검색 하는 더 많은 반사 하지 않습니다.  Generic을 사용 하 여 해당 이벤트를 등록 하는 코드 또한 <xref:System.Windows.WeakEventManager%602> 더 보다는 기존에 사용 하 여 세부 정보 표시 또는 사용자 지정 <xref:System.Windows.WeakEventManager>.|  
|강력 하지 않은 사용자 지정 이벤트 매니저 클래스 만들기|사용자 지정 <xref:System.Windows.WeakEventManager> 때 하면 기존에 <xref:System.Windows.WeakEventManager> 를 사용할 수 없는 및 효율성을 극대화 합니다.  사용자 지정을 사용 하 여 <xref:System.Windows.WeakEventManager> 구독 하는 이벤트 보다 효율적으로 수 있지만 앞에 더 많은 코드를 작성 하는 비용이 발생 하지 합니다.|  
  
 다음 섹션에서는 약한 이벤트 패턴을 구현 하는 방법에 설명 합니다.  이 논의의 목적을 위해 구독 하는 이벤트는 다음과 같은 특징이 있습니다.  
  
-   이벤트 이름 `SomeEvent`.  
  
-   이벤트가 발생 하는 `EventSource` 클래스입니다.  
  
-   이벤트 핸들러가 형식: `SomeEventEventHandler` \(또는 `EventHandler<SomeEventEventArgs>`\).  
  
-   이벤트의 형식 매개 변수 전달 `SomeEventEventArgs` 이벤트 처리기입니다.  
  
### 기존 약한 이벤트 매니저 클래스를 사용 하 여  
  
1.  기존의 약한 이벤트 관리자를 찾습니다.  
  
     상속 계층 구조에서 WPF에 포함 된 약한 이벤트 관리자 목록을 참조는 <xref:System.Windows.WeakEventManager> 클래스입니다.  
  
2.  새로운 약한 이벤트 관리자는 일반 이벤트 후크를 사용 합니다.  
  
     예를 들어, 다음 패턴을 코드를 사용 하 여 이벤트에 등록 하는 경우  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     다음과 같은 패턴을 변경 합니다.  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     마찬가지로, 코드를 다음 패턴을 사용 하 여 이벤트를 구독 취소 합니다 경우:  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     다음과 같은 패턴을 변경 합니다.  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### 일반 약한 이벤트 매니저 클래스를 사용 하 여  
  
1.  Generic을 사용 <xref:System.Windows.WeakEventManager%602> 는 일반 이벤트 후크 대신 클래스입니다.  
  
     사용 하는 경우 <xref:System.Windows.WeakEventManager%602> 이벤트 리스너를 등록 하려면 이벤트 소스를 제공 하 고 <xref:System.EventArgs> 형식으로 형식 매개 변수는 클래스와 호출을 <xref:System.Windows.WeakEventManager%602.AddHandler%2A> 다음 코드와 같이:  
  
    ```  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### 사용자 지정 약한 이벤트 매니저 클래스 만들기  
  
1.  다음 클래스 템플릿을 프로젝트에 복사 합니다.  
  
     이 클래스는 <xref:System.Windows.WeakEventManager> 클래스에서 상속됩니다.  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2.  대체는 `SomeEventWeakEventManager` 이름과 사용자 이름.  
  
3.  해당 이름이 이벤트를 앞에서 설명한 세 가지 이름으로 대체 합니다.  \(`SomeEvent`, `EventSource`, and `SomeEventEventArgs`\)  
  
4.  관리 이벤트와 동일 하 게 표시 하려면 약한 이벤트 매니저 클래스의 가시성 \(공용 \/ 내부 \/ 개인\)를 설정 합니다.  
  
5.  새로운 약한 이벤트 관리자는 일반 이벤트 후크를 사용 합니다.  
  
     예를 들어, 다음 패턴을 코드를 사용 하 여 이벤트에 등록 하는 경우  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     다음과 같은 패턴을 변경 합니다.  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     마찬가지로, 코드를 다음 패턴을 사용 하 여 이벤트를 구독 취소 합니다 경우:  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     다음과 같은 패턴을 변경 합니다.  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## 참고 항목  
 <xref:System.Windows.WeakEventManager>   
 <xref:System.Windows.IWeakEventListener>   
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)