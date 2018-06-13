---
title: 다중 스레드 프로시저의 매개 변수 및 반환 값(C#)
ms.date: 07/20/2015
ms.assetid: ba63c30c-d9f0-4962-b5c7-9d83ba851e6a
ms.openlocfilehash: e27f8e67ff03260e1d13fa633064efc2059e6bdf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340218"
---
# <a name="parameters-and-return-values-for-multithreaded-procedures-c"></a>다중 스레드 프로시저의 매개 변수 및 반환 값(C#)
스레드 클래스의 생성자에 인수를 사용하지 않고 값을 반환하지 않는 프로시저에 대한 참조를 전달해야 하기 때문에 다중 스레드 응용 프로그램에서 값을 제공하고 반환하는 작업은 복잡합니다. 다음 섹션에서는 매개 변수를 제공하고 별도 스레드의 프로시저에서 값을 반환하는 몇 가지 간단한 방법을 보여 줍니다.  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a>다중 스레드 프로시저에 대한 매개 변수 제공  
 다중 스레드 메서드 호출에 대한 매개 변수를 제공하는 최상의 방법은 대상 메서드를 클래스에 래핑하고 새 스레드에 대한 매개 변수로 사용할 해당 클래스의 필드를 정의하는 것입니다. 이 방법의 장점은 새 스레드를 시작할 때마다 해당 매개 변수를 사용하여 클래스의 새 인스턴스를 만들 수 있다는 것입니다. 예를 들어 다음 코드와 같이 삼각형의 면적을 계산하는 함수가 있다고 가정합니다.  
  
```csharp  
double CalcArea(double Base, double Height)  
{  
    return 0.5 * Base * Height;  
}  
```  
  
 다음과 같이 `CalcArea` 함수를 래핑하고 입력 매개 변수를 저장할 필드를 만드는 클래스를 작성할 수 있습니다.  
  
```csharp  
class AreaClass  
{  
    public double Base;  
    public double Height;  
    public double Area;  
    public void CalcArea()  
    {  
        Area = 0.5 * Base * Height;  
        MessageBox.Show("The area is: " + Area.ToString());  
    }  
}  
```  
  
 `AreaClass`를 사용하려면 `AreaClass` 개체를 만들고 `Base` 및 `Height` 속성을 다음 코드와 같이 설정할 수 있습니다.  
  
```csharp  
protected void TestArea()  
{  
    AreaClass AreaObject = new AreaClass();  
  
    System.Threading.Thread Thread =  
        new System.Threading.Thread(AreaObject.CalcArea);  
    AreaObject.Base = 30;  
    AreaObject.Height = 40;  
    Thread.Start();  
}  
```  
  
 `TestArea` 프로시저는 `CalcArea` 메서드를 호출한 후 `Area` 필드의 값을 확인하지 않습니다. `CalcArea`는 별도 스레드에서 실행되기 때문에 `Thread.Start`를 호출한 후 즉시 확인하는 경우 `Area` 필드가 설정되어 있지 않을 수도 있습니다. 다음 섹션에서는 다중 스레드 프로시저에서 값을 반환하는 더 나은 방법을 설명합니다.  
  
## <a name="returning-values-from-multithreaded-procedures"></a>다중 스레드 프로시저에서 값 반환  
 프로시저는 함수일 수 없고 `ByRef` 인수를 사용할 수 없다는 사실 때문에 별도 스레드에서 실행되는 프로시저에서 값을 반환하는 작업은 복잡합니다. 값을 반환하는 가장 쉬운 방법은 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 사용하여 스레드를 관리하고 작업이 완료되면 이벤트를 발생시킨 다음 이벤트 처리기에서 결과를 처리하는 것입니다.  
  
 다음 예제에서는 별도 스레드에서 실행 중인 프로시저에서 이벤트를 발생시켜 값을 반환합니다.  
  
```csharp  
class AreaClass2  
{  
    public double Base;  
    public double Height;  
    public double CalcArea()  
    {  
        // Calculate the area of a triangle.  
        return 0.5 * Base * Height;  
    }  
}  
  
private System.ComponentModel.BackgroundWorker BackgroundWorker1  
    = new System.ComponentModel.BackgroundWorker();  
  
private void TestArea2()  
{  
    InitializeBackgroundWorker();  
  
    AreaClass2 AreaObject2 = new AreaClass2();  
    AreaObject2.Base = 30;  
    AreaObject2.Height = 40;  
  
    // Start the asynchronous operation.  
    BackgroundWorker1.RunWorkerAsync(AreaObject2);  
}  
  
private void InitializeBackgroundWorker()  
{  
    // Attach event handlers to the BackgroundWorker object.  
    BackgroundWorker1.DoWork +=  
        new System.ComponentModel.DoWorkEventHandler(BackgroundWorker1_DoWork);  
    BackgroundWorker1.RunWorkerCompleted +=  
        new System.ComponentModel.RunWorkerCompletedEventHandler(BackgroundWorker1_RunWorkerCompleted);  
}  
  
private void BackgroundWorker1_DoWork(  
    object sender,  
    System.ComponentModel.DoWorkEventArgs e)  
{  
    AreaClass2 AreaObject2 = (AreaClass2)e.Argument;  
    // Return the value through the Result property.  
    e.Result = AreaObject2.CalcArea();  
}  
  
private void BackgroundWorker1_RunWorkerCompleted(  
    object sender,  
    System.ComponentModel.RunWorkerCompletedEventArgs e)  
{  
    // Access the result through the Result property.  
    double Area = (double)e.Result;  
    MessageBox.Show("The area is: " + Area.ToString());  
}  
```  
  
 매개 변수를 제공하고 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> 메서드의 선택적 `ByVal` 상태 개체 변수를 사용하여 스레드 풀 스레드에 값을 반환할 수 있습니다. 스레드 타이머 스레드도 이 용도의 상태 개체를 지원합니다. 스레드 풀링 및 스레드 타이머에 대한 자세한 내용은 [스레드 풀링(C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md) 및 [스레드 타이머(C#)](../../../../csharp/programming-guide/concepts/threading/thread-timers.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [연습: BackgroundWorker 구성 요소를 사용한 다중 스레딩(C#)](../../../../csharp/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)  
 [스레드 풀링(C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md)  
 [스레드 동기화(C#)](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)  
 [이벤트](../../../../csharp/programming-guide/events/index.md)  
 [다중 스레드 응용 프로그램(C#)](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)  
 [대리자](../../../../csharp/programming-guide/delegates/index.md)  
 [구성 요소에서 다중 스레딩](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)
