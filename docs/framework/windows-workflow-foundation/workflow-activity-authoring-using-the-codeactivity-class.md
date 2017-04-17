---
title: "CodeActivity 클래스를 사용하여 워크플로 활동 제작 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cfe315c1-f86d-43ec-b9ce-2f8c469b1106
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# CodeActivity 클래스를 사용하여 워크플로 활동 제작
<xref:System.Activities.CodeActivity>에서 상속하여 만들어진 활동은 <xref:System.Activities.CodeActivity.Execute%2A> 메서드를 재정의하여 기본 명령형 동작을 구현합니다.  
  
## CodeActivityContext 사용  
 <xref:System.Activities.CodeActivityContext> 형식의 `context` 매개 변수 멤버를 사용하여 <xref:System.Activities.CodeActivity.Execute%2A> 메서드에서 워크플로 런타임 기능에 액세스할 수 있습니다.<xref:System.Activities.CodeActivityContext>를 통해 사용할 수 있는 기능은 다음과 같습니다.  
  
-   변수와 인수의 값 가져오기 및 설정  
  
-   <xref:System.Activities.CodeActivityContext.Track%2A>을 사용하는 사용자 지정 추적 기능  
  
-   <xref:System.Activities.CodeActivityContext.GetProperty%2A>을 사용하여 활동의 실행 속성에 액세스  
  
#### CodeActivity에서 상속되는 사용자 지정 활동을 만들려면  
  
1.  [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]을 엽니다.  
  
2.  **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.**프로젝트 형식** 창의 **Visual C\#** 아래에서 **Workflow 4.0**을 선택하고 **v2010** 노드를 선택합니다.**템플릿** 창에서 **활동 라이브러리**를 선택합니다.새 프로젝트의 이름을 HelloActivity로 지정합니다.  
  
3.  HelloActivity 프로젝트에서 Activity1.xaml을 마우스 오른쪽 단추로 클릭하고 **삭제**를 선택합니다.  
  
4.  HelloActivity 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**, **클래스**를 차례로 선택합니다.새 프로젝트의 이름을 HelloActivity.cs로 지정합니다.  
  
5.  HelloActivity.cs 파일에서 다음 `using` 지시문을 추가합니다.  
  
    ```csharp  
    using System.Activities;  
    using System.Activities.Statements;  
    ```  
  
6.  기본 클래스를 클래스 선언에 추가하여 <xref:System.Activities.CodeActivity>에서 새 클래스를 상속하도록 합니다.  
  
    ```csharp  
    class HelloActivity : CodeActivity  
    ```  
  
7.  <xref:System.Activities.CodeActivity.Execute%2A> 메서드를 추가하여 클래스에 기능을 추가합니다.  
  
    ```csharp  
    protected override void Execute(CodeActivityContext context)  
    {  
        Console.WriteLine("Hello World!");  
    }  
    ```  
  
8.  <xref:System.Activities.CodeActivityContext>를 사용하여 추적 레코드를 만듭니다.  
  
    ```csharp  
    protected override void Execute(CodeActivityContext context)  
    {  
        Console.WriteLine("Hello World!");  
        CustomTrackingRecord record = new CustomTrackingRecord("MyRecord");  
        record.Data.Add(new KeyValuePair<String, Object>("ExecutionTime", DateTime.Now));  
        context.Track(record);  
    }  
  
    ```