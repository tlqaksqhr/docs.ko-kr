---
title: '방법: 인터페이스 이벤트 구현(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], event implementation in classes
- events [C#], in interfaces
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
ms.openlocfilehash: 7437868bffa0f317ad29ed6c920ae007c602defa
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874883"
---
# <a name="how-to-implement-interface-events-c-programming-guide"></a>방법: 인터페이스 이벤트 구현(C# 프로그래밍 가이드)
[인터페이스](../../../csharp/language-reference/keywords/interface.md)는 [이벤트](../../../csharp/language-reference/keywords/event.md)를 선언할 수 있습니다. 다음 예제에서는 클래스에서 인터페이스 이벤트를 구현하는 방법을 보여 줍니다. 기본적인 규칙은 다른 모든 인터페이스 메서드나 속성을 구현할 때의 규칙과 같습니다.  
  
## <a name="to-implement-interface-events-in-a-class"></a>클래스에서 인터페이스 이벤트를 구현하려면  
  
클래스에서 이벤트를 선언한 다음 적절한 영역에서 이벤트를 호출합니다.  
  
```csharp
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
            ShapeChanged?.Invoke(this, e);  
        }  
    }  

}  
```  
  
## <a name="example"></a>예  
다음 예제에서는 클래스가 둘 이상의 인터페이스에서 상속을 받으며 각 인터페이스에는 이름이 같은 이벤트가 있는 드문 상황을 처리하는 방법을 보여 줍니다. 이러한 상황에서는 이벤트 하나 이상에 대해 명시적 인터페이스 구현을 제공해야 합니다. 이벤트에 대한 명시적 인터페이스 구현을 쓸 때는 `add` 및 `remove` 이벤트 접근자도 써야 합니다. 일반적으로는 컴파일러가 이러한 접근자를 제공하지만 이 예제의 경우에는 컴파일러가 접근자를 제공할 수 없습니다.  
  
고유한 접근자를 제공하면 클래스에서 두 이벤트를 같은 이벤트로 표시할지 아니면 다른 이벤트로 표시할지를 지정할 수 있습니다. 예를 들어 인터페이스 사양에 따라 이벤트가 서로 다른 시간에 발생해야 하는 경우에는 각 이벤트를 클래스의 개별 구현과 연결할 수 있습니다. 다음 예제에서는 구독자가 `IShape` 또는 `IDrawingObject`에 셰이프 참조를 캐스팅하여 수신할 `OnDraw` 이벤트를 결정합니다.  
  
 [!code-csharp[WrapTwoInterfaceEvents](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-implement-interface-events_1.cs#everything)]
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [이벤트](../../../csharp/programming-guide/events/index.md)  
 [대리자](../../../csharp/programming-guide/delegates/index.md)  
 [명시적 인터페이스 구현](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)  
 [방법: 파생 클래스에서 기본 클래스 이벤트 발생](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)
