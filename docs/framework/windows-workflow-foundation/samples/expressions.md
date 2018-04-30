---
title: Expressions2
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43a85905-77b5-4893-bb38-1cb9b293d69d
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c8470a3bb93385724f50e18d25c148ee609c3a77
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="expressions"></a>식
이 샘플에서는 워크플로에서 기본 식을 사용하는 방법을 보여 줍니다. 이 샘플은 가상 회사의 직원 두 명에 대한 기본 급여 통계를 계산하는 워크플로로 구성되어 있습니다. 두 개의 클래스(`Employee` 및 `SalaryStats`)가 Employee.cs와 SalaryStats.cs에 정의되어 있습니다. 이 두 클래스는 복합 형식의 변수 속성에 대한 단순 산술 연산 및 문자열 연산을 수행하는 방법을 보여 주는 워크플로에서 사용됩니다.  
  
 급여 계산 워크플로는 XAML과 C#으로 정의되어 두 작성 스타일을 보여 줍니다. XAML 버전은 SalaryCalculation.xaml에 포함되어 있고 Workflow Designer에서 보거나 편집할 수 있습니다. C# 버전은 Program.cs에 있습니다. XAML에서 사용되는 식은 Visual Basic 구문을 따르고 <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> 및 <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> 식 활동을 사용하여 실행됩니다. Visual Basic 식 참조 하는 방법에 대 한 자세한 내용은 [Visual Basic 식을](http://go.microsoft.com/fwlink/?LinkId=165912)합니다. 반면에 C#의 식은 람다 식으로 작성되고 <xref:System.Activities.Expressions.LambdaValue%601> 및 <xref:System.Activities.Expressions.LambdaReference%601> 식 활동을 사용합니다. 람다 식으로 식을 작성하면 C# 컴파일러에서 구문 강조 표시 기능과 정적 확인 기능을 제공할 수 있습니다. C#의 람다 식에 대 한 자세한 내용은 참조 하십시오. [람다 식 (C# 프로그래밍 가이드)](http://go.microsoft.com/fwlink/?LinkId=182082)합니다. Visual Basic을 사용하는 코드에서 워크플로를 제작한 경우 Visual Basic 람다 식이 사용됩니다. Visual Basic의 람다 식에 대 한 자세한 내용은 참조 [람다 식 (Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=152437)합니다. 코드를 사용 하 여 워크플로 작성 하는 방법에 대 한 방법에 대 한 자세한 내용은 참조 [제작 워크플로, 활동 및 식을 사용 하 여 명령적 코드](../../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md)합니다.  
  
#### <a name="to-run-the-sample"></a>이 샘플을 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 Expressions.sln 솔루션을 엽니다.  
  
2.  솔루션을 작성 하거나 선택 하려면 CTRL + SHIFT + B를 눌러 **솔루션 빌드** 에서 **빌드** 메뉴.  
  
    > [!NOTE]
    >  Visual Studio 디자이너에서 SalaryCalculation.xaml을 열려면 먼저 프로젝트를 컴파일하여 디자이너에서 `Employee` 및 `SalaryStats` 클래스를 사용할 수 있는지 확인해야 합니다.  
  
3.  빌드가 성공한 후 F5 키를 누르거나 선택 **디버깅 시작** 에서 **디버그** 메뉴. Ctrl + f 5를 눌러 하거나 선택할 수 또는 **디버깅 하지 않고 시작** 에서 **디버그** 메뉴 디버깅 없이 실행 합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Expressions`