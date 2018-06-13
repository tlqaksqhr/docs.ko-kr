---
title: 절대 지연
ms.date: 03/30/2017
ms.assetid: b483139a-39bb-4560-8003-8969a8fc2cd1
ms.openlocfilehash: 3a104f6b879e9cdc899bad2201ad1ed320a38a2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518387"
---
# <a name="absolute-delay"></a>절대 지연
이 샘플의 주요 시나리오는 워크플로 응용 프로그램에서 지속형 타이머를 사용하여 지정된 <xref:System.DateTime>까지 지연하는 것입니다. 지정된 <xref:System.Activities.Statements.Delay>(또는 분/초 수) 동안만 지연할 수 있다는 점에서 이 샘플은 기본 제공 <xref:System.TimeSpan> 작업을 사용하는 것과는 다릅니다.  
  
 다음과 같은 일부 실제 시나리오에서는 이러한 차이를 구분해야 합니다.  
  
1.  오류가 없음을 확인하기 위해 메일 전송을 30초 동안 지연하려고 합니다.  
  
2.  야근을 하고 있으며 정상 업무 시간(예: 오전 8시)까지 모든 메일을 지연하려고 합니다.  
  
## <a name="demonstrates"></a>세부 항목  
  
1.  <xref:System.Activities.Statements.DurableTimerExtension>을 사용하여 절대 지연 구현  
  
2.  <xref:System.Activities.WorkflowApplication>을 사용하여 지속성 타이머에 대해 지속성 설정  
  
3.  <xref:System.Activities.NativeActivity%601>를 통해 확장성 지점 사용  
  
4.  SendEmail 작업에서 <xref:System.Activities.CodeActivity%601> 사용  
  
5.  <xref:System.Activities.Statements.Delay>  
  
6.  XAML 전용 워크플로  
  
 이 샘플에서는 <xref:System.DateTime>을 받아들이고 지속형 타이머를 사용하여 지연 기간을 등록하는 사용자 지정 작업을 만드는 방법을 보여 줍니다. 지속형 타이머를 사용하는 경우 책갈피를 타이머 확장에 등록해야 하므로 <xref:System.Activities.NativeActivity>를 사용하여 해당 책갈피를 만들어야 합니다. 이 샘플에서는 지속형 타이머가 만료될 경우 `OnTimerExpired` 메서드가 호출됩니다. 런타임에 이 정보를 제공하려면 <xref:System.Activities.NativeActivity%601.CacheMetadata%2A> 이벤트에 타이머 확장을 추가해야 합니다. 기타 구현 세부 정보는 <xref:System.DateTime>에서 <xref:System.TimeSpan>으로 변환할 논리를 구현해야 한다는 것뿐입니다. 지속형 타이머는 <xref:System.DateTime>만 받아들이기 때문입니다. 이 경우 정확도가 약간 저하됩니다.  
  
> [!NOTE]
>  <xref:System.DateTime>에서 <xref:System.TimeSpan>으로 변환하면 정확도가 약간 손실됩니다.  
  
 이 샘플에서는 <xref:System.Activities.WorkflowApplication>에 대해 지속성을 설정하는 방법도 보여 줍니다. 이 특정 샘플에서는 타이머가 만료될 때까지 기다리는 유휴 시간 동안 워크플로 데이터가 지속성 데이터베이스에 언로드되는 지속형 타이머를 사용합니다. 다른 지속성 동작에 이 구현을 사용할 수도 있습니다. 이 샘플에서는 SQL Server로 지속성 연결 문자열을 설정하는 방법 및 워크플로 인스턴스에 대한 데이터를 저장하기 위해 인스턴스 저장소를 만드는 방법을 보여 줍니다. 워크플로 인스턴스를 실행 가능하게 만드는 이벤트가 발생한 후 워크플로를 다시 시작하는 방법에 대한 논리가 제공됩니다.  
  
 이 샘플을 실행 하는 대로 기본 제공 지연이 시작 되 고 완료 되 면를 차례로 시간 전자 메일 메시지를 보내도록 하면 표시 됩니다. 여기서 AbsoluteDelay 작업은 지정한 <xref:System.DateTime>(또는 <xref:System.DateTime>이 만료된 경우 0초) 전까지 중지되며, 만료 시 전자 메일이 전송됩니다. 이 샘플에서는 기본 제공 <xref:System.Activities.Statements.Delay> 기능의 두 가지 사용 사례를 AbsoluteDelay 작업 사용과 비교하여 보여 줍니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  SQL Server Express 이상이 컴퓨터에 설치되었는지 확인합니다.  
  
2.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트의 WF/Basic/Services/AbsoluteDelay/CS에서 setup.cmd를 실행하여 AbsoluteDelaySampleDB 데이터베이스, 지속성 스키마 및 지속성 논리를 만듭니다.  
  
3.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 솔루션을 엽니다.  
  
4.  지연 작업의 기간을 지정합니다.  
  
5.  AbsoluteDelay 작업의 ExpirationTime을 지정합니다.  
  
6.  SendMail 작업의 SendMailTo, SendMailFrom, SendMailSubject, SendMailBody 및 SmtpHost 필드를 업데이트합니다.  
  
    > [!NOTE]
    >  올바른 SMTP 호스트를 입력하지 않으면 응용 프로그램에서 SMTP 예외를 throw합니다.  
  
7.  선택 하 여 솔루션을 빌드합니다 **빌드**, **솔루션 빌드**합니다.  
  
8.  키를 눌러 솔루션을 실행 **F5**합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\AbsoluteDelay`
