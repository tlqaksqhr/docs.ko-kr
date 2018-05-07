---
title: 보정 가능한 활동 샘플
ms.date: 03/30/2017
ms.assetid: 58f4898c-b2b8-44a4-9a73-3bef4da6d5ba
ms.openlocfilehash: 8008eaaca062723cab1efabfb1b25018353c73b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compensable-activity-sample"></a>보정 가능한 활동 샘플
이 샘플에서는 `CompensableActivity` 활동을 사용하여 정상적인 실행 중에 지정된 동작에 대해 수행할 작업과 해당 동작을 보정하기 위해 필요한 경우 나중에 수행해야 하는 작업을 정의하는 방법을 보여 줍니다.  샘플의 첫 번째 부분에서는 보정 가능한 작업 단위를 정의할 수 있는 방법을에서 Windows WF (Workflow Foundation)을 보여 줍니다. 사용 하는 `CompensableActivity` 활동 및 실행을 성공적으로 실행 하는 방법입니다.  샘플의 두 번째 부분에서는 예기치 않은 이벤트가 발생하고 워크플로 인스턴스가 취소될 경우 동일한 보정 가능 작업 단위가 자동으로 보정을 처리하는 방법을 보여 줍니다.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  Visual Studio 2010을 사용하여 CompensableActivity.sln을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  F5 키를 눌러 응용 프로그램을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\BasicCompensableActivity`