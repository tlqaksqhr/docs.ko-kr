---
title: Load From XAML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f103ef6-7bed-4f16-ae52-9e665c5a43d7
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ca5f830e666ad65ca2162ffd1abb03ce9beca387
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="load-from-xaml"></a>Load From XAML
이 샘플에서는 XamlBuildTask 도구를 실행할 필요 없이 XAML 워크플로를 동적으로 로드하는 방법을 보여 줍니다. 이 샘플에서는 대신 <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> 메서드를 호출합니다. 이 샘플은 [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] 클래스를 사용하여 XAML 워크플로를 로드하고 이를 실행하는 <xref:System.Activities.XamlIntegration.ActivityXamlServices> 클라이언트 응용 프로그램입니다. <xref:System.Activities.XamlIntegration.ActivityXamlServices> 클래스를 사용하여 XAML 워크플로를 로드한 후에는 실행할 수 있는 <xref:System.Activities.DynamicActivity%601>가 반환됩니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 LoadFromXAML.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl+F5를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\LoadFromXAML`  
  
## <a name="see-also"></a>참고 항목
