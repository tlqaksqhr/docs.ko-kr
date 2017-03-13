---
title: "방법: 인터페이스 이벤트 구현(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "이벤트[C#], 인터페이스의"
  - "인터페이스[C#], 클래스에서 이벤트 구현"
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# 방법: 인터페이스 이벤트 구현(C# 프로그래밍 가이드)
[인터페이스](../../../csharp/language-reference/keywords/interface.md)에서는 [이벤트](../../../csharp/language-reference/keywords/event.md)를 선언할 수 있습니다.  다음 예제에서는 클래스에 인터페이스 이벤트를 구현하는 방법을 보여 줍니다.  기본적으로 규칙은 인터페이스 메서드나 속성을 구현할 때와 동일합니다.  
  
### 클래스에 인터페이스 이벤트를 구현하려면  
  
-   클래스에 이벤트를 선언하고 이를 적절한 영역에서 호출합니다.  
  
    ```  
    namespace ImplementInterfaceEvents  
    {  
        public interface IDrawingObject  
        {  
            event EventHandler ShapeChanged;  
        }  
        public class MyEventArgs : EventArgs   
        {  
            // class members  
        }  
        public class Shape : IDrawingObject  
        {  
            public event EventHandler ShapeChanged;  
            void ChangeShape()  
            {  
                // Do something here before the event…  
  
                OnShapeChanged(new MyEventArgs(/*arguments*/));  
  
                // or do something here after the event.   
            }  
            protected virtual void OnShapeChanged(MyEventArgs e)  
            {  
                if(ShapeChanged != null)  
                {  
                   ShapeChanged(this, e);  
                }  
            }  
        }  
  
    }  
    ```  
  
## 예제  
 다음 예제에서는 클래스가 두 개 이상의 인터페이스에서 상속되며 각 인터페이스에 동일한 이름의 이벤트가 있는 보다 덜 일반적인 경우를 처리하는 방법을 보여 줍니다.  이 경우 하나 이상의 이벤트에 대해 명시적으로 인터페이스를 구현해야 합니다.  이벤트에 대한 명시적 인터페이스 구현을 작성할 때는 `add` 및 `remove` 이벤트 접근자를 작성해야 합니다.  일반적으로 이러한 접근자는 컴파일러에서 제공되지만 이 경우에는 컴파일러에서 제공할 수 없습니다.  
  
 사용자 고유의 접근자를 제공하면 두 이벤트를 클래스의 동일한 이벤트가 나타낼지 각기 다른 이벤트가 나타낼지를 지정할 수 있습니다.  예를 들어, 인터페이스 사양에 따라 다른 시간에 이벤트를 발생시켜야 하는 경우에는 클래스에 있는 별도의 구현에 각 이벤트를 연결할 수 있습니다.  다음 예제에서는 구독자가 `IShape` 또는 `IDrawingObject`에 대한 모양 참조를 캐스팅하여 수신할 `OnDraw` 이벤트를 결정합니다.  
  
 [!code-cs[csProgGuideEvents#10](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-implement-interface-events_1.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [이벤트](../../../csharp/programming-guide/events/index.md)   
 [대리자](../../../csharp/programming-guide/delegates/index.md)   
 [명시적 인터페이스 구현](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)   
 [방법: 파생 클래스에서 기본 클래스 이벤트 발생](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)