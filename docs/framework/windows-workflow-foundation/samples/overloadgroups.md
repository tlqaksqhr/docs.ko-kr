---
title: OverloadGroups
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d1d547d2-f5fb-4de3-a959-ee6139a4f1ad
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f644f09af3ce9e191dc6c5680472de4ef5ab727d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="overloadgroups"></a>OverloadGroups
이 샘플은 눈여겨 봐야 할 두 가지 특징을 지닌 활동(`CreateLocation`)으로 구성되어 있습니다.  
  
1.  이 활동에는 몇 가지 필수 인수와 몇 가지 선택적 인수가 있습니다.  
  
2.  이 활동에서 서로 다른 두 가지 인수 집합 중 하나를 선택할 수 있습니다.  
  
 이러한 동작을 수행하는 데는 다음과 같은 두 가지 기능이 사용됩니다.  
  
-   `[isRequired]`는 특정 활동의 속성이 할당되었는지 여부를 검사하고, 속성이 할당되지 않았으면 예외를 throw합니다.  
  
-   `[OverloadGroup]`은 인수 집합을 함께 묶어 활동 사용자가 특정 집합을 선택하여 사용할 수 있도록 합니다. 동일한 인스턴스 내에서 다른 오버로드 그룹의 인수를 사용할 수는 없습니다.  
  
 다른 워크플로를 설정하고 나면 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>의 <xref:System.Activities.Validation.ValidationResults> 컬렉션을 반환하는 <xref:System.Activities.Validation.Constraint>를 호출합니다. <xref:System.Activities.Validation.Constraint> 개체를 콘솔에 출력합니다.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  열기는 **OverloadGroups.sln** 샘플 솔루션을 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]합니다.  
  
2.  솔루션을 빌드하고 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\OverloadGroups`
