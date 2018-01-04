---
title: "ByteStream 인코더"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e674a8ab-f79a-4a93-b984-54b34392dafc
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: de6d5fd64046a72eb6a21b43dd977463f5619850
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="bytestream-encoder"></a><span data-ttu-id="6d3e5-102">ByteStream 인코더</span><span class="sxs-lookup"><span data-stu-id="6d3e5-102">ByteStream Encoder</span></span>
<span data-ttu-id="6d3e5-103">이 샘플에서는 바이트 스트림 인코더의 기능을 보여 주는 `ByteStreamHttpBinding`인 <xref:System.ServiceModel.Channels.Binding>의 작성 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6d3e5-103">This sample demonstrates how to create a `ByteStreamHttpBinding`, a <xref:System.ServiceModel.Channels.Binding> that demonstrates the functionality of the byte stream encoder.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="6d3e5-104">토론</span><span class="sxs-lookup"><span data-stu-id="6d3e5-104">Discussion</span></span>  
 <span data-ttu-id="6d3e5-105">이 샘플에서는 표준 바인딩 요소 <xref:System.ServiceModel.Channels.Binding> 및 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>를 사용하여 표준 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>을 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6d3e5-105">This sample demonstrates how to create a standard <xref:System.ServiceModel.Channels.Binding> using the standard binding elements <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> and <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span></span> <span data-ttu-id="6d3e5-106">또한 바이트 스트림 인코더를 사용하여 이미지를 업로드 및 다운로드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6d3e5-106">This sample shows how to use the byte stream encoder to upload and download an image.</span></span> <span data-ttu-id="6d3e5-107">바이트 스트림 인코더 기능은 HTTP 전송만 지원하며 신뢰할 수 있는 메시징 또는 보안과 같은 기능은 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d3e5-107">The byte stream encoder feature only supports the HTTP transport and it does not support features such as reliable messaging or security.</span></span> <span data-ttu-id="6d3e5-108">지원되는 <xref:System.ServiceModel.Channels.MessageVersion>은 <xref:System.ServiceModel.Channels.MessageVersion.None%2A>뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="6d3e5-108">The only <xref:System.ServiceModel.Channels.MessageVersion> supported is <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6d3e5-109">[!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] 또는 [!INCLUDE[win7_client_firstref](../../../../includes/win7-client-firstref-md.md)]에서 이 샘플을 실행하는 경우 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]이 높은 권한으로 실행 중인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3e5-109">If you are running this sample in [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] or [!INCLUDE[win7_client_firstref](../../../../includes/win7-client-firstref-md.md)], ensure that you are running [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] with elevated privileges.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6d3e5-110">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d3e5-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6d3e5-111">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="6d3e5-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6d3e5-112">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="6d3e5-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6d3e5-113">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d3e5-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\ByteStreamEncoder`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6d3e5-114">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="6d3e5-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="6d3e5-115">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 ByteStreamHttpBinding.sln 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6d3e5-115">Open the ByteStreamHttpBinding.sln file in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="6d3e5-116">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 하 여 ByteStreamHttpBindingServer 프로젝트의 새 인스턴스를 시작 **디버그**, 차례로 **새 인스턴스 시작** 상황에 맞는 메뉴입니다.</span><span class="sxs-lookup"><span data-stu-id="6d3e5-116">Start a new instance of the ByteStreamHttpBindingServer project by right-clicking the project in the Solution Explorer and selecting **Debug**, and then **Start new instance** from the context menu.</span></span>  
  
3.  <span data-ttu-id="6d3e5-117">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 하 여 ByteStreamHttpBindingClient 프로젝트의 새 인스턴스를 시작 **디버그**, **새 인스턴스 시작** 상황에 맞는 메뉴입니다.</span><span class="sxs-lookup"><span data-stu-id="6d3e5-117">Start a new instance of the ByteStreamHttpBindingClient project by right-clicking the project in the Solution Explorer and selecting **Debug**, **Start new instance** from the context menu.</span></span>
