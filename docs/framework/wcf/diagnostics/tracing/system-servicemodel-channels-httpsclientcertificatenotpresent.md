---
title: System.ServiceModel.Channels.HttpsClientCertificateNotPresent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b13ef1b6-e340-401d-93ca-2710c3842205
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1808015cd310e64ac05e9827a229112ddd76a80f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelshttpsclientcertificatenotpresent"></a><span data-ttu-id="7e117-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span><span class="sxs-lookup"><span data-stu-id="7e117-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span></span>
<span data-ttu-id="7e117-103">클라이언트 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7e117-103">Client certificate is required.</span></span> <span data-ttu-id="7e117-104">요청에서 인증서를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e117-104">No certificate was found in the request.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7e117-105">설명</span><span class="sxs-lookup"><span data-stu-id="7e117-105">Description</span></span>  
 <span data-ttu-id="7e117-106">이 추적은 HTTPS 수신기가 클라이언트 인증서에 연결되지 않은 HTTPS 요청을 받았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7e117-106">This trace indicates that the HTTPS listener received an HTTPS request that was not associated with a client certificate.</span></span> <span data-ttu-id="7e117-107">수신기가 모든 HTTPS 요청에서 클라이언트 인증서를 요구하도록 구성되어 있기 때문에 수신기가 클라이언트 인증의 유효성을 검사하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="7e117-107">Since the listener was configured to require client certificates on all HTTPS requests, the listener failed to validate the client’s authenticity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e117-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e117-108">See Also</span></span>  
 [<span data-ttu-id="7e117-109">추적</span><span class="sxs-lookup"><span data-stu-id="7e117-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="7e117-110">추적을 사용 하 여 응용 프로그램 문제를 해결 하려면</span><span class="sxs-lookup"><span data-stu-id="7e117-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="7e117-111">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="7e117-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
