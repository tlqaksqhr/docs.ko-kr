---
title: ClickOnce를 사용하여 WCF 응용 프로그램 배포
ms.date: 03/30/2017
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
ms.openlocfilehash: ceb652eed1a7cc377538f5d693dcb85ed99da4b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456698"
---
# <a name="deploying-wcf-applications-with-clickonce"></a><span data-ttu-id="d56c4-102">ClickOnce를 사용하여 WCF 응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="d56c4-102">Deploying WCF Applications with ClickOnce</span></span>
<span data-ttu-id="d56c4-103">Windows Communication Foundation (WCF)를 사용 하 여 클라이언트 응용 프로그램은 ClickOnce 기술을 사용 하 여 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d56c4-103">Client applications using Windows Communication Foundation (WCF) may be deployed using ClickOnce technology.</span></span> <span data-ttu-id="d56c4-104">클라이언트 응용 프로그램이 신뢰할 수 있는 인증서를 사용하여 디지털 방식으로 서명되는 경우, 이 기술을 통해 클라이언트 응용 프로그램은 코드 액세스 보안에서 제공하는 런타임 보안 보호의 이점을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d56c4-104">This technology allows them to take advantage of the runtime security protections provided by Code Access Security, provided that they are digitally signed with a trusted certificate.</span></span> <span data-ttu-id="d56c4-105">ClickOnce 응용 프로그램 서명에 사용되는 인증서는 신뢰할 수 있는 게시자 저장소에 있어야 하며, 클라이언트 컴퓨터의 로컬 보안 정책은 게시자의 인증서를 사용하여 서명된 응용 프로그램에 완전 신뢰 권한을 부여하도록 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d56c4-105">The certificate used to sign the ClickOnce application must reside in the Trusted Publisher store, and the local security policy on the client machine must be configured to grant Full Trust permissions to applications signed with the publisher's certificate.</span></span>  
  
 <span data-ttu-id="d56c4-106">ClickOnce 응용 프로그램 및 신뢰할 수 있는 게시자 구성에 대 한 참조 [ClickOnce 신뢰할 수 있는 게시자 구성](http://go.microsoft.com/fwlink/?LinkId=94774)합니다.</span><span class="sxs-lookup"><span data-stu-id="d56c4-106">For information on configuring ClickOnce applications and trusted publishers, see [Configuring ClickOnce Trusted Publishers](http://go.microsoft.com/fwlink/?LinkId=94774).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d56c4-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d56c4-107">See Also</span></span>  
 [<span data-ttu-id="d56c4-108">신뢰할 수 있는 응용 프로그램 배포 개요</span><span class="sxs-lookup"><span data-stu-id="d56c4-108">Trusted Application Deployment Overview</span></span>](http://go.microsoft.com/fwlink/?LinkId=94775)  
 [<span data-ttu-id="d56c4-109">ClickOnce 배포에 대 한 Windows Forms 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="d56c4-109">ClickOnce Deployment for Windows Forms Applications</span></span>](http://go.microsoft.com/fwlink/?LinkId=94776)
