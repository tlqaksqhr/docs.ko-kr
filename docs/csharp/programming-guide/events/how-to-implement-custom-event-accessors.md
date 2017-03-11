---
title: "방법: 사용자 지정 이벤트 접근자 구현(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "접근자[C#], 이벤트 접근자"
  - "add 접근자[C#]"
  - "이벤트[C#], add 접근자"
  - "이벤트[C#], remove 접근자"
  - "remove 접근자[C#]"
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
caps.latest.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 7
---
# 방법: 사용자 지정 이벤트 접근자 구현(C# 프로그래밍 가이드)
이벤트는 해당 이벤트가 선언된 클래스에서만 호출할 수 있는 특수한 종류의 멀티캐스트 대리자입니다.  클라이언트 코드에서는 이벤트가 발생할 때 호출되어야 하는 메서드에 대한 참조를 제공하여 이벤트를 구독합니다.  이러한 메서드는 이벤트 접근자를 통해 대리자의 호출 목록에 추가됩니다. 명명된 `add` 및 `remove`가 있다는 것을 제외하면 이벤트 접근자는 속성 접근자와 유사합니다.  대부분의 경우 사용자 지정 이벤트 접근자를 제공할 필요가 없습니다.  코드에 사용자 지정 이벤트 접근자를 제공하지 않으면 컴파일러가 자동으로 추가합니다.  하지만 사용자 지정 동작을 제공해야 하는 경우도 있습니다.  이러한 예를 보려면 [방법: 인터페이스 이벤트 구현](../../../csharp/programming-guide/events/how-to-implement-interface-events.md) 항목을 참조하십시오.  
  
## 예제  
 다음 예제에서는 사용자 지정 add 및 remove 이벤트 접근자를 구현하는 방법을 보여 줍니다.  접근자 내의 코드는 마음대로 바꿀 수 있지만 새 이벤트 처리기 메서드를 추가하거나 제거하기 전에 이벤트를 잠그는 것이 좋습니다.  
  
```  
event EventHandler IDrawingObject.OnDraw  
        {  
            add  
            {  
                lock (PreDrawEvent)  
                {  
                    PreDrawEvent += value;  
                }  
            }  
            remove  
            {  
                lock (PreDrawEvent)  
                {  
                    PreDrawEvent -= value;  
                }  
            }  
        }  
  
```  
  
## 참고 항목  
 [이벤트](../../../csharp/programming-guide/events/index.md)   
 [event](../../../csharp/language-reference/keywords/event.md)