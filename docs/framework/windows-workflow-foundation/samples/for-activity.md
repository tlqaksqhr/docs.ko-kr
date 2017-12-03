---
title: "For 활동"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ea751b4-36f0-48aa-a115-70a2ab89f6d8
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b3b97e4bcd8dd60aa2768a8346d120bdebdb55ba
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="for-activity"></a>For 활동
For 샘플에서는 <xref:System.Activities.NativeActivity>에서 상속되는 사용자 지정 활동을 빌드한 후 워크플로에서 해당 활동을 사용하여 실제 예제를 실행하는 방법을 보여 줍니다. 이 샘플에 포함된 사용자 지정 활동은 C# `for` 문처럼 작동합니다. T  
  
 `For` 사용자 지정 활동에는 각각 표준 C# `InitAction` 문의 초기화 문, 반복 문, 연속 조건 및 본문에 해당하는 `IterationAction`, `Condition`, `Body` 및 `For`라는 속성이 있습니다.  
  
 다음 표에서는 샘플의 키 파일에 대해 설명합니다.  
  
|파일|설명|  
|----------|-----------------|  
|For.cs|`For` 클래스를 확장하여 C# <xref:System.Activities.NativeActivity> 문의 기능을 제공하는 `For` 사용자 지정 활동에 대한 클래스 정의입니다.|  
|Program.cs|사용자 지정 `For` 활동을 사용하여 컬렉션에 대한 기본 반복 작업을 수행하는 클라이언트 응용 프로그램입니다.|  
  
> [!NOTE]
>  `For` 사용자 지정 활동을 사용할 때는 `Condition` 속성이 설정되어 있는지 확인해야 합니다. 설정되어 있지 않으면 무한 루프가 발생할 수 있습니다.  
  
## <a name="demonstrates"></a>세부 항목  
 <xref:System.Activities.NativeActivity>에서 상속되는 사용자 지정 활동을 만듭니다.  
  
## <a name="discussion"></a>토론  
 다음 표에서는 이 샘플에 포함된 활동의 속성에 대해 설명합니다.  
  
 InitAction  
 초기화 문  
  
 IterationAction  
 반복 문  
  
 조건  
 연속 문  
  
 Body  
 본문  
  
 활동은 <xref:System.Activities.NativeActivity>에서 상속되어 `ScheduleActivity`의 <xref:System.Activities.NativeActivityContext> 메서드 중 하나를 사용하여 실행할 추가 활동 예약과 같은 런타임 기능에 대한 액세스 권한을 얻습니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 For.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  F5 키를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\For`