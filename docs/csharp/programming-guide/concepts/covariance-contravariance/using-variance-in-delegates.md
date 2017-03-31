---
title: "대리자의 가변성 사용(C#) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 1638c95d-dc8b-40c1-972c-c2dcf84be55e
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fbcf08eafe05e3299379b0455640fc08ec80e0ca
ms.lasthandoff: 03/13/2017

---
# <a name="using-variance-in-delegates-c"></a>대리자의 가변성 사용(C#)
메서드를 대리자에 할당하면 *공변성(covariance)* 및 *반공변성(Contravariance)*은 대리자 형식과 메서드 시그니처의 일치를 확인하는 유연성을 제공합니다. 공변성(covariance)은 메서드가 대리자에 정의된 것보다 더 많은 수의 파생된 형식을 반환하도록 허용합니다. 반공변성(contravariance)은 메서드가 대리자 형식보다 더 적은 수의 파생된 매개 변수 형식을 갖도록 허용합니다.  
  
## <a name="example-1-covariance"></a>예제 1: 공변성(Covariance)  
  
### <a name="description"></a>설명  
 이 예제에서는 대리자를 대리자 시그니처의 반환 형식에서 파생된 반환 형식이 있는 메서드와 함께 사용하는 방법을 보여 줍니다. `DogsHandler`에서 반환된 데이터 형식은 `Dogs`이고, 이 형식은 대리자에 정의된 `Mammals` 형식에서 파생됩니다.  
  
### <a name="code"></a>코드  
  
```csharp  
class Mammals{}  
class Dogs : Mammals{}  
  
class Program  
{  
    // Define the delegate.  
    public delegate Mammals HandlerMethod();  
  
    public static Mammals MammalsHandler()  
    {  
        return null;  
    }  
  
    public static Dogs DogsHandler()  
    {  
        return null;  
    }  
  
    static void Test()  
    {  
        HandlerMethod handlerMammals = MammalsHandler;  
  
        // Covariance enables this assignment.  
        HandlerMethod handlerDogs = DogsHandler;  
    }  
}  
```  
  
## <a name="example-2-contravariance"></a>예제 2: 반공변성(Contravariance)  
  
### <a name="description"></a>설명  
 이 예제에서는 대리자를 대리자 시그니처 매개 변수 형식의 기본 형식인 형식 매개 변수를 가지고 있는 메서드와 함께 사용하는 방법을 보여 줍니다. 반공변성(contravariance)에서는 별도의 여러 처리기 대신 하나의 이벤트 처리기를 사용할 수 있습니다. 예를 들어 `EventArgs` 입력 매개 변수를 수락하고, 매개 변수로서 `MouseEventArgs` 형식을 전송하는 `Button.MouseClick` 이벤트 및 `KeyEventArgs` 매개 변수를 전송하는 `TextBox.KeyDown` 이벤트와 함께 사용하는 이벤트 처리기를 만들 수 있습니다.  
  
### <a name="code"></a>코드  
  
```csharp  
// Event hander that accepts a parameter of the EventArgs type.  
private void MultiHandler(object sender, System.EventArgs e)  
{  
    label1.Text = System.DateTime.Now.ToString();  
}  
  
public Form1()  
{  
    InitializeComponent();  
  
    // You can use a method that has an EventArgs parameter,  
    // although the event expects the KeyEventArgs parameter.  
    this.button1.KeyDown += this.MultiHandler;  
  
    // You can use the same method   
    // for an event that expects the MouseEventArgs parameter.  
    this.button1.MouseClick += this.MultiHandler;  
  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [대리자의 가변성(C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)   
 [Func 및 Action 제네릭 대리자에 가변성 사용(C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
