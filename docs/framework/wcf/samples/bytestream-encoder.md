---
title: "ByteStream 인코더 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e674a8ab-f79a-4a93-b984-54b34392dafc
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# ByteStream 인코더
이 샘플에서는 바이트 스트림 인코더의 기능을 보여 주는 <xref:System.ServiceModel.Channels.Binding>인 `ByteStreamHttpBinding`의 작성 방법을 보여 줍니다.  
  
## 토론  
 이 샘플에서는 표준 바인딩 요소 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> 및 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>를 사용하여 표준 <xref:System.ServiceModel.Channels.Binding>을 작성하는 방법을 보여 줍니다.  또한 바이트 스트림 인코더를 사용하여 이미지를 업로드 및 다운로드하는 방법을 보여 줍니다.  바이트 스트림 인코더 기능은 HTTP 전송만 지원하며 신뢰할 수 있는 메시징 또는 보안과 같은 기능은 지원하지 않습니다.  지원되는 <xref:System.ServiceModel.Channels.MessageVersion>은 <xref:System.ServiceModel.Channels.MessageVersion.None%2A>뿐입니다.  
  
> [!IMPORTANT]
>  [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] 또는 [!INCLUDE[win7_client_firstref](../../../../includes/win7-client-firstref-md.md)]에서 이 샘플을 실행하는 경우 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]이 높은 권한으로 실행 중인지 확인합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.  계속하기 전에 다음\(기본\) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [.NET Framework 4용 WCF\(Windows Communication Foundation\) 및 Windows WF\(Workflow Foundation\) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780)\(영문\)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.  이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\ByteStreamEncoder`  
  
#### 샘플을 설치, 빌드 및 실행하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 ByteStreamHttpBinding.sln 파일을 엽니다.  
  
2.  솔루션 탐색기에서 ByteStreamHttpBindingServer 프로젝트를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **디버그**를 선택한 다음 **새 인스턴스 시작**을 선택하여 이 프로젝트의 새 인스턴스를 시작합니다.  
  
3.  솔루션 탐색기에서 ByteStreamHttpBindingClient 프로젝트를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **디버그**를 선택한 다음 **새 인스턴스 시작**을 선택하여 이 프로젝트의 새 인스턴스를 시작합니다.