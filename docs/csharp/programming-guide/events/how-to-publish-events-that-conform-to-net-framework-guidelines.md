---
title: "방법: .NET Framework 지침을 따르는 이벤트 게시(C# 프로그래밍 가이드) | Microsoft Docs"
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
  - "이벤트[C#], 구현 지침"
ms.assetid: 9310ae16-8627-44a2-b08c-05e5976202b1
caps.latest.revision: 31
caps.handback.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 방법: .NET Framework 지침을 따르는 이벤트 게시(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

다음 절차에서는 사용자의 클래스와 구조체에 표준 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 패턴을 따르는 이벤트를 추가하는 방법을 보여 줍니다.  [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 클래스 라이브러리의 모든 이벤트는 다음과 같이 정의된 <xref:System.EventHandler> 대리자를 기반으로 합니다.  
  
```  
public delegate void EventHandler(object sender, EventArgs e);  
```  
  
> [!NOTE]
>  [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)]에서는 이 대리자의 제네릭 버전인 <xref:System.EventHandler%601>이 도입되었습니다.  다음 예제에서는 두 버전을 모두 사용하는 방법을 보여 줍니다.  
  
 클래스의 이벤트를 정의할 때 값을 반환하는 대리자까지 포함하여 모든 올바른 대리자 형식을 기반으로 할 수 있지만 일반적으로는 다음 예제와 같이 <xref:System.EventHandler>를 사용하여 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 패턴을 기반으로 이벤트를 정의하는 것이 좋습니다.  
  
### EventHandler 패턴을 기반으로 하는 이벤트를 게시하려면  
  
1.  이벤트를 사용하여 사용자 지정 데이터를 보낼 필요가 없는 경우에는 이 단계를 건너뛰고 3a단계로 이동합니다. 게시자 클래스와 구독자 클래스 모두에 표시되는 범위에서 사용자 지정 데이터의 클래스를 선언합니다.  그런 다음 사용자 지정 이벤트 데이터를 보관할 필수 멤버를 추가합니다.  이 예제에서는 간단한 문자열이 반환됩니다.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
2.  제네릭 버전의 <xref:System.EventHandler%601>을 사용하는 경우 이 단계를 건너뜁니다. 게시 클래스에서 대리자를 선언합니다.  대리자에 *EventHandler*로 끝나는 이름을 지정합니다.  두 번째 매개 변수는 사용자 지정 EventArgs 형식을 지정합니다.  
  
    ```  
    public delegate void CustomEventHandler(object sender, CustomEventArgs a);  
    ```  
  
3.  다음 단계 중 하나를 사용하여 게시 클래스에 이벤트를 선언합니다.  
  
    1.  사용자 지정 EventArgs 클래스가 없으면 이벤트 형식은 제네릭이 아닌 EventHandler 대리자가 됩니다.  C\# 프로젝트를 만들 때 포함된 <xref:System> 네임스페이스에는 대리자가 이미 선언되어 있으므로 대리자를 선언할 필요가 없습니다.  게시자 클래스에 다음 코드를 추가합니다.  
  
        ```  
        public event EventHandler RaiseCustomEvent;  
        ```  
  
    2.  제네릭이 아닌 버전의 <xref:System.EventHandler>를 사용하고 있고 <xref:System.EventArgs>에서 파생된 사용자 지정 클래스가 있는 경우에는 게시 클래스 내에서 이벤트를 선언하고 2단계의 대리자를 해당 형식으로 사용합니다.  
  
        ```  
        public event CustomEventHandler RaiseCustomEvent;  
  
        ```  
  
    3.  제네릭 버전을 사용하는 경우에는 사용자 지정 대리자가 필요하지 않습니다.  대신 게시 클래스에서 꺾쇠괄호 사이 사용자 고유의 클래스 이름을 대체하여 이벤트 형식을 `EventHandler<CustomEventArgs>`로 지정합니다.  
  
        ```  
        public event EventHandler<CustomEventArgs> RaiseCustomEvent;  
        ```  
  
## 예제  
 다음 예제에서는 사용자 지정 EventArgs 클래스를 사용하고 이벤트 형식으로 <xref:System.EventHandler%601>을 사용하여 앞에서 설명한 단계를 보여 줍니다.  
  
 [!CODE [csProgGuideEvents#2](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideEvents#2)]  
  
## 참고 항목  
 <xref:System.Delegate>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [이벤트](../../../csharp/programming-guide/events/index.md)   
 [대리자](../../../csharp/programming-guide/delegates/index.md)