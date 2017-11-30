---
title: "기본 활동 구성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c283a1a7-1245-4ecd-8072-206c1b4ca379
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9e8a4255eed0b957aaa5be16a807ab07d78e9fa1
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2017
---
# <a name="basic-activity-composition"></a>기본 활동 구성
이 샘플에서는 사용자 지정 활동을 추가로 빌드하기 위해 사용자 지정 활동과 시스템 제공 활동을 구성하는 방법을 보여 줍니다.  
  
 설문 조사 활동을 사용하는 워크플로에서 질문 목록을 준비하여 설문 조사 일정을 예약한 다음 설문을 통해 수집된 응답을 출력합니다.  
  
## <a name="sample-details"></a>샘플 세부 정보  
 이 샘플에서는 다음과 같이 세 개의 사용자 지정 활동을 사용합니다. `ReadLine`단순 <xref:System.Activities.NativeActivity> \<문자열 > 만들어지는 <xref:System.Activities.Bookmark> 예약 되 고 다음을 설정 하는 경우는 `Return` <xref:System.Activities.OutArgument%601> 되는 값으로 하는 <xref:System.Activities.Bookmark> 다시 시작 됩니다. `Prompt`이 <xref:System.Activities.Activity%601> \<문자열 >를 사용 하는 <xref:System.Activities.InArgument%601>< 문자열\> 라는 `Text` 사용자의 응답을 반환 하 고는 `Result` <xref:System.Activities.OutArgument%601> \<문자열 > 합니다. `Prompt` 활동에는 .NET Framework의 일부로 제공되는 <xref:System.Activities.Statements.Sequence> 및 <xref:System.Activities.Statements.WriteLine> 활동이 사용되며, 사용자로부터 입력을 받기 위한 사용자 지정 `ReadLine` 활동도 여기에 통합됩니다. 마지막 사용자 지정 활동은 `Survey` 활동입니다. 한 <xref:System.Activities.Activity>< c t i o\<문자열 >> 합니다.  이 활동에서는 <xref:System.Activities.InArgument%601>< a b l e < 문자열\>> 라는 `Questions` 채웁니다는 `Result` out 인수에 응답 합니다. `Survey` 활동에는 .NET Framework의 <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Sequence> 및 <xref:System.Activities.Statements.AddToCollection%601>이 사용되며, 설문 조사 문항을 묻고 응답을 얻기 위한 `Prompt` 활동도 사용됩니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  열기는 **BasicActivityComposition.sln** 샘플 솔루션을 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]합니다.  
  
2.  솔루션을 빌드하고 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\ActivityComposition`