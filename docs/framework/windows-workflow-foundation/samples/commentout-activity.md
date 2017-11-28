---
title: "CommentOut 활동"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 340204c3-f827-45fb-870e-55e2ac457ca5
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: df5faa2aacf6b86d708dad4b157b27d2609a0a93
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="commentout-activity"></a>CommentOut 활동
이 샘플에서는 다른 활동을 사실상 주석으로 처리하여 실행 경로에서 제거하는 사용자 지정 활동을 작성하는 방법을 보여 줍니다.  
  
## <a name="the-commentout-activity"></a>CommentOut 활동  
 목표를 달성하기 위해 CommentOut 활동은 <xref:System.Activities.CodeActivity> 기본 클래스에서 파생되며 빈 <xref:System.Activities.CodeActivity.Execute%2A> 메서드를 구현합니다.  
  
```  
protected override void Execute(CodeActivityContext context)  
{  
}  
```  
  
 다음 예제와 같이 클래스를 선언합니다.  
  
```  
[Designer(typeof(CommentOutDesigner))]  
[ContentProperty("Body")]  
public sealed class CommentOut : CodeActivity  
```  
  
 `Designer` 특성은 디자인 타임에 활동의 시각적 인터페이스를 구현하는 클래스를 지정합니다. `ContentProperty` 특성은 이 활동의 인스턴스에 대한 XAML 표현에서 `"Body"` 속성을 건너뛸 수 있다고 선언합니다.  
  
```  
<Border x:Uid="Border_1" BorderThickness ="1">  
    <sad:WorkflowItemPresenter   
    x:Uid="sad:WorkflowItemPresenter_1" AutomationProperties.AutomationId="Body" Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"  
    AllowedItemType="{x:Type sa:Activity}"  
    HintText="Drop activity here"   
    Margin="5,5,5,5" />  
</Border>  
```  
  
 디자이너 클래스에서 XAML은 활동의 사용자 지정 시각적 표현을 만드는 데 사용됩니다. <xref:System.Activities.Presentation.WorkflowItemPresenter>는 시각적 편집기를 제공하는 클래스입니다.  
  
 단일 활동을 `CommentOut` 활동 화면에 끌어 놓을 수 있습니다. 이 화면에 여러 활동을 추가하려면 먼저 Sequence 활동을 여기에 끌어 옵니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 CommentOut.sln을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 컴파일합니다.  
  
3.  Ctrl+F5를 눌러 디버깅 없이 샘플을 시작합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\CommentOut`
