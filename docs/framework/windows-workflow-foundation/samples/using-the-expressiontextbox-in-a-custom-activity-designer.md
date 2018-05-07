---
title: 사용자 지정 활동 디자이너에서 ExpressionTextBox 사용
ms.date: 03/30/2017
ms.assetid: f82e73e7-a256-4a4d-82b7-c0d62f4ab5e7
ms.openlocfilehash: ad0c29e2661c82e663fd6b68fdcd74f542ef28b1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="using-the-expressiontextbox-in-a-custom-activity-designer"></a>사용자 지정 활동 디자이너에서 ExpressionTextBox 사용
이 샘플에서는 사용자 지정 활동 디자이너에서 <xref:System.Activities.Presentation.View.ExpressionTextBox>를 사용하는 방법을 보여 줍니다. 사용자 지정 활동인 `MultiAssign`은 두 개의 문자열 변수에 두 개의 문자열 값을 할당합니다. <xref:System.Activities.Presentation.View.ExpressionTextBox> 컨트롤 중 일부는 <xref:System.Activities.InArgument>에 바인딩되고 또 다른 일부는 <xref:System.Activities.OutArgument>에 바인딩됩니다.  
  
## <a name="sample-details"></a>샘플 세부 정보  
 `ArgumentToExpressionConverter`는 식을 인수에 바인딩할 때 사용되는 형식 변환기입니다. `ConverterParameter`는 `In` 또는 `Out`으로 적절히 설정해야 합니다. `InOut`은 지원되지 않습니다.  
  
 `UseLocationExpression` 특성이 사용 될 `OutArgument`식이 l-value ("왼쪽된 값" 또는 "위치 값") 식 여야 한다고 지정 하도록 합니다. 대부분의 경우 L-value 식은 반환되는 `OutArgument`가 변수인지 인수 이름인지를 나타내는 데 사용되는 유효한 Visual Basic 식별자입니다.  
  
 이 예제에서 `MaxLines` 특성은 1로 설정되어 있으며 `MinLines`는 설정되어 있지 않습니다. 이는 사용자가 입력하는 테스트 크기에 관계없이 <xref:System.Activities.Presentation.View.ExpressionTextBox>는 한 줄이라는 고정된 크기임을 나타냅니다. <xref:System.Activities.Presentation.View.ExpressionTextBox>를 사용자 입력에 맞춰 늘릴 수 있게 하려면 `MaxLines`를 `MinLines`보다 큰 값으로 설정합니다.  
  
 ExpressionTextBox는 인수에만 바인딩할 수 있고 CLR 속성에는 바인딩할 수 없습니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 ExpressionTextBoxSample.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
#### <a name="to-run-this-sample"></a>이 샘플을 실행하려면  
  
1.  솔루션에 워크플로 콘솔 응용 프로그램을 추가합니다.  
  
2.  에 대 한 참조 추가 **ExpressionTextBoxSample** 새 워크플로 콘솔 응용 프로그램 프로젝트에서 프로젝트.  
  
3.  솔루션을 빌드합니다.  
  
4.  끌어서는 **MultiAssign** 도구 상자에서 활동을 워크플로에 놓습니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\ExpressionTextBox`  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Activities.Presentation.View.ExpressionTextBox>  
 [워크플로 디자이너로 응용 프로그램 개발](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
