---
title: WCF에 필요한 운영 체제 리소스
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: 4522f1c59c8f74281a0e197338c6206ab29c229b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498646"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="164bb-102">WCF에 필요한 운영 체제 리소스</span><span class="sxs-lookup"><span data-stu-id="164bb-102">Operating System Resources Required by WCF</span></span>
<span data-ttu-id="164bb-103">Windows Communication Foundation (WCF) 함수에 운영 체제에서 제공 되는 여러 리소스에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="164bb-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="164bb-104">다음 표에서는 이러한 리소스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="164bb-104">The following table lists those resources.</span></span>  
  
|<span data-ttu-id="164bb-105">리소스</span><span class="sxs-lookup"><span data-stu-id="164bb-105">Resource</span></span>|<span data-ttu-id="164bb-106">설명</span><span class="sxs-lookup"><span data-stu-id="164bb-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="164bb-107">MSDTC(Microsoft Distributed Transaction Coordinator)</span><span class="sxs-lookup"><span data-stu-id="164bb-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="164bb-108">OleTx 트랜잭션을 지원하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="164bb-108">Required to support OleTx transactions.</span></span>|  
|<span data-ttu-id="164bb-109">IIS(인터넷 정보 서비스)</span><span class="sxs-lookup"><span data-stu-id="164bb-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="164bb-110">IIS를 사용하여 응용 프로그램을 호스트하려는 경우에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="164bb-110">Required if you want to use IIS to host your application.</span></span>|  
|<span data-ttu-id="164bb-111">WAS(Windows Process Activation Service)</span><span class="sxs-lookup"><span data-stu-id="164bb-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="164bb-112">WAS를 사용하여 응용 프로그램을 호스트하려는 경우에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="164bb-112">Required if you want to use WAS to host your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="164bb-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="164bb-113">See Also</span></span>  
 [<span data-ttu-id="164bb-114">시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="164bb-114">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)
