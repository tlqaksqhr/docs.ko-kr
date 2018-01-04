---
title: "NativeActivity 기본 클래스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 254a4c50-425b-426d-a32f-0f7234925bac
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e53471a2d0245b1547ae5ee3c3a147e024aedefb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="nativeactivity-base-class"></a>NativeActivity 기본 클래스
<xref:System.Activities.NativeActivity>는 protected 생성자를 가진 추상 클래스입니다. <xref:System.Activities.CodeActivity>와 마찬가지로 <xref:System.Activities.NativeActivity>는 <xref:System.Activities.NativeActivity.Execute%2A> 메서드를 구현하여 필수 동작을 작성하는 데 사용됩니다. <xref:System.Activities.CodeActivity>와 달리 <xref:System.Activities.NativeActivity>는 <xref:System.Activities.NativeActivityContext> 메서드에 전달되는 <xref:System.Activities.NativeActivity.Execute%2A> 개체를 통해 워크플로 런타임의 모든 노출된 기능에 액세스할 수 있습니다.  
  
## <a name="using-nativeactivitycontext"></a>NativeActivityContext 사용  
 <xref:System.Activities.NativeActivity.Execute%2A> 형식의 `context` 매개 변수 멤버를 사용하여 <xref:System.Activities.NativeActivityContext> 메서드에서 워크플로 런타임 기능에 액세스할 수 있습니다. <xref:System.Activities.NativeActivityContext>를 통해 사용할 수 있는 기능은 다음과 같습니다.  
  
-   인수 및 변수 가져오기 및 설정  
  
-   <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>를 사용하여 자식 활동 예약  
  
-   <xref:System.Activities.NativeActivityContext.Abort%2A>를 사용하여 활동 실행 중단  
  
-   <xref:System.Activities.NativeActivityContext.CancelChild%2A> 및 <xref:System.Activities.NativeActivityContext.CancelChildren%2A>을 사용하여 자식 실행 취소  
  
-   <xref:System.Activities.NativeActivityContext.CreateBookmark%2A>, <xref:System.Activities.NativeActivityContext.RemoveBookmark%2A>, <xref:System.Activities.NativeActivityContext.ResumeBookmark%2A> 등과 같은 메서드를 사용하여 활동 책갈피 액세스  
  
-   <xref:System.Activities.CodeActivityContext.Track%2A>을 사용하는 사용자 지정 추적 기능  
  
-   <xref:System.Activities.CodeActivityContext.GetProperty%2A> 및 <xref:System.Activities.NativeActivityContext.GetValue%2A>를 사용하여 활동 실행 속성 및 값 속성 액세스  
  
-   <xref:System.Activities.NativeActivityContext.ScheduleAction%2A> 및 <xref:System.Activities.NativeActivityContext.ScheduleFunc%2A>을 사용하여 활동 동작 및 기능 예약  
  
#### <a name="to-create-a-custom-activity-that-inherits-from-nativeactivity"></a>NativeActivity에서 상속되는 사용자 지정 활동을 만들려면  
  
1.  [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]를 엽니다.  
  
2.  선택 **파일**, **새**, 차례로 **프로젝트**합니다. 선택 **Workflow 4.0** 아래 **Visual C#** 에 **프로젝트 형식** 창과 선택은 **v2010** 노드. 선택 **활동 라이브러리** 에 **템플릿** 창. 새 프로젝트의 이름을 HelloActivity로 지정합니다.  
  
3.  HelloActivity 프로젝트에서 Activity1.xaml을 마우스 오른쪽 단추로 클릭 하 고 선택 **삭제**합니다.  
  
4.  HelloActivity 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가**, 차례로 **클래스**합니다. 새 프로젝트의 이름을 HelloActivity.cs로 지정합니다.  
  
5.  HelloActivity.cs 파일에서 다음 `using` 지시문을 추가합니다.  
  
    ```csharp  
    using System.Activities;  
    using System.Activities.Statements;  
    ```  
  
6.  기본 클래스를 클래스 선언에 추가하여 새 클래스를 <xref:System.Activities.NativeActivity>에서 상속하도록 설정합니다.  
  
    ```csharp  
    class HelloActivity : NativeActivity  
    ```  
  
7.  <xref:System.Activities.NativeActivity.Execute%2A> 메서드를 추가하여 클래스에 기능을 추가합니다.  
  
    ```csharp  
    protected override void Execute(NativeActivityContext context)  
    {  
        Console.WriteLine("Hello World!");  
    }  
    ```  
  
8.  <xref:System.Activities.NativeActivity.CacheMetadata%2A> 메서드를 재정의하고 적합한 Add 메서드를 호출하여 워크플로 런타임에서 사용자 지정 활동의 변수, 인수, 자식 및 대리자를 알 수 있도록 합니다. 자세한 내용은 <xref:System.Activities.NativeActivityMetadata> 클래스를 참조하세요.  
  
9. <xref:System.Activities.NativeActivityContext> 개체를 사용하여 책갈피를 예약합니다. 책갈피를 만들고 예약하고 다시 시작하는 방법은 <xref:System.Activities.WorkflowApplicationIdleEventArgs.Bookmarks%2A>를 참조하세요.  
  
    ```  
    protected override void Execute(NativeActivityContext context)  
        {  
            // Create a Bookmark and wait for it to be resumed.  
            context.CreateBookmark(BookmarkName.Get(context),   
                new BookmarkCallback(OnResumeBookmark));  
        }  
    ```
