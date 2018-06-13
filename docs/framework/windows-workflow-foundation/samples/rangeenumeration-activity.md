---
title: RangeEnumeration 활동
ms.date: 03/30/2017
ms.assetid: ca5b78f4-94fa-4aa7-830d-26039ac422c8
ms.openlocfilehash: 9aa04c80f20e2d410fb49e2d07d836c8c5ab1b4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516580"
---
# <a name="rangeenumeration-activity"></a>RangeEnumeration 활동
이 샘플에서는 숫자 컬렉션을 반복하는 사용자 지정 활동을 만드는 방법을 보여 줍니다. 다음 표에는 이 샘플에 포함된 주요 파일에 대한 세부 사항이 나와 있습니다.  
  
|파일 이름|설명|  
|---------------|-----------------|  
|RangeEnumeration.cs|`RangeEnumeration` 클래스를 재정의하고 일련의 숫자를 반복하는 <xref:System.Activities.NativeActivity>이라는 사용자 지정 활동을 정의합니다.|  
|RangeEnumerationSample.cs|`RangeEnumeration` 활동을 사용하여 숫자 컬렉션을 반복하는 클라이언트 응용 프로그램입니다.|  
  
 다음 표에는 `RangeEnumeration` 활동의 속성에 대한 자세한 설명이 나와 있습니다.  
  
|속성|설명|  
|--------------|-----------------|  
|시작|루프를 시작할 정수입니다.|  
|중지|루프를 중지할 정수입니다.|  
|단계|반복 과정에서 매번 얼마나 진행할지 지정합니다.|  
|Body|각 반복 과정에서 실행할 코드를 지정합니다.|  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 RangeEnumeration.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl+F5를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\RangeEnumeration`