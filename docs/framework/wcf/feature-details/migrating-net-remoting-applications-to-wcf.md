---
title: .NET Remoting 응용 프로그램을 WCF로 마이그레이션
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: 53f63352503a48ee849580e676b5fe98f3dcf2cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33492498"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a><span data-ttu-id="f10c5-102">.NET Remoting 응용 프로그램을 WCF로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="f10c5-102">Migrating .NET Remoting Applications to WCF</span></span>
<span data-ttu-id="f10c5-103">**이 항목은 이전 버전의 기존 응용 프로그램과의 호환성을 위해 유지되며 새로운 개발에 권장되지 않는 레거시 기술과 관련된 것입니다. 이제 WCF를 사용 하 여 분산된 응용 프로그램을 개발 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f10c5-103">**This topic is specific to a legacy technology that is retained for backward compatibility with existing applications and is not recommended for new development. Distributed applications should now be developed using WCF.**</span></span>  
  
 <span data-ttu-id="f10c5-104">두 가지 방법으로 기존.NET Remoting 응용 프로그램과 함께 WCF 활용 하기 위해: 통합과 마이그레이션입니다.</span><span class="sxs-lookup"><span data-stu-id="f10c5-104">There are two ways to take advantage of WCF with existing .NET Remoting applications: integration and migration.</span></span> <span data-ttu-id="f10c5-105">통합을 사용 하면.net Remoting 2.0 및를 실행 하는 WCF 쪽, 측에 의해에서는 기존.Net 수정 하지 않고도 동시에 두 기술을 통해 동일한 비즈니스 개체를 표시할 수 있도록 하지만 Remoting 2.0 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="f10c5-105">Integration allows you to have .Net Remoting 2.0 and WCF running side by side, letting you expose the same business objects over both technologies simultaneously without having to modify your existing .Net Remoting 2.0 code.</span></span> <span data-ttu-id="f10c5-106">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 이상에서 실행해야 통합을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f10c5-106">Integration requires that you are running on [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 or greater.</span></span> <span data-ttu-id="f10c5-107">WCF 기능을 활용 하려고 하지만 Remoting 2.0 시스템과 유선 호환성은 필요 하지 않는 하는 경우 전체 서비스를 WCF로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f10c5-107">If you want to take advantage of WCF features and do not need wire compatibility with Remoting 2.0 systems, you can migrate your entire service to WCF.</span></span> <span data-ttu-id="f10c5-108">.NET Remoting 2.0 으로부터 WCF로 마이그레이션 원격 개체의 인터페이스 및 해당 구성 설정을 변경 해야합니다.</span><span class="sxs-lookup"><span data-stu-id="f10c5-108">Migration from .NET Remoting 2.0 to WCF requires changes to the remote object's interface and its configuration settings.</span></span> <span data-ttu-id="f10c5-109">이 항목에 설명 되어 [에서 원격 Windows Communication Foundation을](http://go.microsoft.com/fwlink/?LinkId=74403)합니다.</span><span class="sxs-lookup"><span data-stu-id="f10c5-109">Both of these topics are covered in [From Remoting to the Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=74403).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f10c5-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f10c5-110">See Also</span></span>  
 [<span data-ttu-id="f10c5-111">개념적 개요</span><span class="sxs-lookup"><span data-stu-id="f10c5-111">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)
