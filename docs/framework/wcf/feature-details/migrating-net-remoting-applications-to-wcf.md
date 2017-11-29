---
title: ".NET Remoting 응용 프로그램을 WCF로 마이그레이션"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dff06fbc52c0f4371abf0bcc465fd6a6d8be5859
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="migrating-net-remoting-applications-to-wcf"></a><span data-ttu-id="2c3b8-102">.NET Remoting 응용 프로그램을 WCF로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="2c3b8-102">Migrating .NET Remoting Applications to WCF</span></span>
<span data-ttu-id="2c3b8-103">**이 항목은 이전 버전의 기존 응용 프로그램과의 호환성을 위해 유지되며 새로운 개발에 권장되지 않는 레거시 기술과 관련된 것입니다. 분산 응용 프로그램은 이제 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]을 사용하여 개발해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="2c3b8-103">**This topic is specific to a legacy technology that is retained for backward compatibility with existing applications and is not recommended for new development. Distributed applications should now be developed using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].**</span></span>  
  
 <span data-ttu-id="2c3b8-104">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 기존 .NET 원격 응용 프로그램과 함께 활용하는 두 가지 방법은 통합과 마이그레이션입니다.</span><span class="sxs-lookup"><span data-stu-id="2c3b8-104">There are two ways to take advantage of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with existing .NET Remoting applications: integration and migration.</span></span> <span data-ttu-id="2c3b8-105">통합 기능은 기존 .Net Remoting 2.0 코드를 수정하지 않고도 동시에 두 가지 기술에 대해 동일한 비즈니스 개체를 노출하도록 하여 사용자가 .Net Remoting 2.0과 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 함께 실행하도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c3b8-105">Integration allows you to have .Net Remoting 2.0 and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] running side by side, letting you expose the same business objects over both technologies simultaneously without having to modify your existing .Net Remoting 2.0 code.</span></span> <span data-ttu-id="2c3b8-106">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 이상에서 실행해야 통합을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c3b8-106">Integration requires that you are running on [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 or greater.</span></span> <span data-ttu-id="2c3b8-107">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 기능을 활용하려고 하지만 Remoting 2.0 시스템과의 유선 호환성은 필요하지 않을 경우, 전체 서비스를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c3b8-107">If you want to take advantage of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] features and do not need wire compatibility with Remoting 2.0 systems, you can migrate your entire service to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="2c3b8-108">.NET Remoting 2.0으로부터 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]로 마이그레이션하려면 원격 개체의 인터페이스 및 해당 구성 설정으로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c3b8-108">Migration from .NET Remoting 2.0 to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requires changes to the remote object's interface and its configuration settings.</span></span> <span data-ttu-id="2c3b8-109">이 항목에 설명 되어 [에서 원격 Windows Communication Foundation을](http://go.microsoft.com/fwlink/?LinkId=74403)합니다.</span><span class="sxs-lookup"><span data-stu-id="2c3b8-109">Both of these topics are covered in [From Remoting to the Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=74403).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c3b8-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c3b8-110">See Also</span></span>  
 [<span data-ttu-id="2c3b8-111">개념적 개요</span><span class="sxs-lookup"><span data-stu-id="2c3b8-111">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)
