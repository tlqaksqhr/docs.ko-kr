---
title: "방법: 이벤트 구독 및 구독 취소(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "코드 편집기, 이벤트 처리기"
  - "이벤트 처리기[C#], 만들기"
  - "이벤트[C#], IDE를 사용하여 만들기"
ms.assetid: 6319f39f-282c-4173-8a62-6c4657cf51cd
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 방법: 이벤트 구독 및 구독 취소(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

다른 클래스에서 게시한 이벤트가 발생할 때 호출되는 사용자 지정 코드를 작성하려면 해당 이벤트를 구독합니다.  예를 들어, 사용자가 단추를 클릭할 때 응용 프로그램에서 필요한 작업을 수행하도록 하려면 해당 단추의 `click` 이벤트를 구독합니다.  
  
### Visual Studio IDE를 사용하여 이벤트를 구독하려면  
  
1.  **속성** 창이 표시되어 있지 않으면 **디자인** 뷰에서 이벤트 처리기를 만들려는 폼이나 컨트롤을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.  
  
2.  **속성** 창의 위쪽에서 **이벤트** 아이콘을 클릭합니다.  
  
3.  `Load` 이벤트 등의 만들려는 이벤트를 두 번 클릭합니다.  
  
     [!INCLUDE[csprcs](../../../csharp/includes/csprcs_md.md)]에서 자동으로 빈 이벤트 처리기 메서드가 만들어져 코드에 추가됩니다.  또는 사용자가 직접 **코드** 뷰에서 코드를 추가할 수 있습니다.  예를 들어, 다음 코드 줄에서는 `Form` 클래스에서 `Load` 이벤트를 발생시킬 때 호출되는 이벤트 처리기 메서드를 선언합니다.  
  
     [!CODE [csProgGuideEvents#11](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideEvents#11)]  
  
     이벤트를 구독하는 데 필요한 코드 줄은 프로젝트의 Form1.Designer.cs 파일에 있는 `InitializeComponent` 메서드에서도 자동으로 생성됩니다.  이 코드 줄은 다음과 같습니다.  
  
    ```  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
### 프로그래밍 방식으로 이벤트를 구독하려면  
  
1.  시그니처가 해당 이벤트의 대리자 시그니처와 일치하는 이벤트 처리기 메서드를 정의합니다.  예를 들어, 이벤트가 <xref:System.EventHandler> 대리자 형식을 기반으로 하는 경우 다음 코드는 메서드 스텁을 나타냅니다.  
  
    ```  
    void HandleCustomEvent(object sender, CustomEventArgs a)  
    {  
       // Do something useful here.  
    }  
    ```  
  
2.  이벤트에 이벤트 처리기를 연결하려면 더하기 할당 연산자\(`+=`\)를 사용합니다.  다음 예제에서는 `publisher` 개체에 `RaiseCustomEvent` 이벤트가 있다고 가정합니다.  구독자 클래스에서 해당 이벤트를 구독하려면 게시자 클래스에 대한 참조가 필요합니다.  
  
    ```  
    publisher.RaiseCustomEvent += HandleCustomEvent;  
    ```  
  
     위의 구문은 C\# 2.0의 새로운 구문입니다.  이 구문에 해당하는 C\# 1.0 구문에서는 `new` 키워드를 사용하여 캡슐화 대리자를 명시적으로 만들어야 합니다.  
  
    ```  
    publisher.RaiseCustomEvent += new CustomEventHandler(HandleCustomEvent);  
    ```  
  
     람다 식을 사용하여 이벤트 처리기를 추가할 수도 있습니다.  
  
    ```  
    public Form1()  
    {  
        InitializeComponent();  
        // Use a lambda expression to define an event handler.  
        this.Click += (s,e) => { MessageBox.Show(  
           ((MouseEventArgs)e).Location.ToString());};  
    }  
    ```  
  
     자세한 내용은 [방법: LINQ 외부에 람다 식 사용](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-lambda-expressions-outside-linq.md)을 참조하십시오.  
  
### 무명 메서드를 사용하여 이벤트를 구독하려면  
  
-   나중에 이벤트에 대한 등록을 취소할 필요가 없는 경우 더하기 할당 연산자\(`+=`\)를 사용하여 이벤트에 무명 메서드를 연결합니다.  다음 예제에서는 `publisher` 개체에 `RaiseCustomEvent`  이벤트가 있으며 몇 가지 특수 이벤트 정보를 전달하도록 `CustomEventArgs` 클래스도 정의되었다고 가정합니다.  구독자 클래스에서 해당 이벤트를 구독하려면 `publisher`에 대한 참조가 필요합니다.  
  
    ```  
    publisher.RaiseCustomEvent += delegate(object o, CustomEventArgs e)  
    {  
      string s = o.ToString() + " " + e.ToString();  
      Console.WriteLine(s);  
    };  
    ```  
  
     익명 함수를 사용하여 이벤트를 구독한 경우 이벤트를 쉽게 구독 취소할 수 없다는 점에 주의하십시오.  이 경우에 이벤트를 구독 취소하려면 이벤트를 구독하는 코드로 돌아가서 대리자 변수에 무명 메서드를 저장하고 이벤트에 대리자를 추가해야 합니다.  일반적으로 코드의 뒷부분에서 이벤트에 대한 구독을 취소해야 한다면 이벤트를 구독하는 데 익명 함수를 사용하지 않는 것이 좋습니다.  익명 함수에 대한 자세한 내용은 [익명 함수](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)를 참조하십시오.  
  
## 구독 취소  
 이벤트가 발생할 때 이벤트 처리기가 호출되지 않도록 하려면 이벤트를 구독 취소합니다.  리소스 누수를 방지하려면 구독자 개체를 삭제하기 전에 이벤트를 구독 취소해야 합니다.  이벤트를 구독 취소하기 전까지 게시 개체에 있는 이벤트의 기반이 되는 멀티캐스트 대리자에는 구독자의 이벤트 처리기를 캡슐화하는 대리자에 대한 참조가 있습니다.  게시 개체에 해당 참조가 포함되어 있는 한 가비지 수집에서 구독자 개체가 삭제되지 않습니다.  
  
#### 이벤트를 구독 취소하려면  
  
-   빼기 할당 연산자\(`-=`\)를 사용하여 이벤트를 구독 취소합니다.  
  
    ```  
    publisher.RaiseCustomEvent -= HandleCustomEvent;  
    ```  
  
     모든 구독자가 이벤트를 구독 취소한 경우 게시자 클래스에 있는 해당 이벤트 인스턴스는 `null`로 설정됩니다.  
  
## 참고 항목  
 [이벤트](../../../csharp/programming-guide/events/index.md)   
 [event](../../../csharp/language-reference/keywords/event.md)   
 [방법: .NET Framework 지침을 따르는 이벤트 게시](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)   
 [\-\= 연산자](../../../csharp/language-reference/operators/subtraction-assignment-operator-1.md)   
 [\+\= 연산자](../../../csharp/language-reference/operators/addition-assignment-operator.md)