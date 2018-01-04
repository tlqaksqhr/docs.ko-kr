---
title: "문제 해결: 서비스 응용 프로그램 성공 &#39; t 설치"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 43c973d83d2d1b614cf0ce49ba8d4af24123b47e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="troubleshooting-service-application-won39t-install"></a><span data-ttu-id="fe378-102">문제 해결: 서비스 응용 프로그램 성공 &#39; t 설치</span><span class="sxs-lookup"><span data-stu-id="fe378-102">Troubleshooting: Service Application Won&#39;t Install</span></span>
<span data-ttu-id="fe378-103">서비스 응용 프로그램이 제대로 설치 되지 않을 경우 확인 되도록 하는 <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> 해당 서비스에 대 한 설치 관리자에 표시 된 대로 서비스 클래스의 속성을 같은 값으로 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe378-103">If your service application will not install correctly, check to make sure that the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for the service class is set to the same value as is shown in the installer for that service.</span></span> <span data-ttu-id="fe378-104">값 올바르게 설치 하기 위해 서비스에 대 한 순서 대로 두 인스턴스 모두에 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe378-104">The value must be the same in both instances in order for your service to install correctly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe378-105">설치 프로세스에 피드백을 받을 설치 로그를 살펴볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe378-105">You can also look at the installation logs to get feedback on the installation process.</span></span>  
  
 <span data-ttu-id="fe378-106">이미 설치 된 동일한 이름의 다른 서비스를 갖고 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe378-106">You should also check to determine whether you have another service with the same name already installed.</span></span> <span data-ttu-id="fe378-107">서비스 이름은 설치에 성공 하려면 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe378-107">Service names must be unique for installation to succeed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe378-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe378-108">See Also</span></span>  
 [<span data-ttu-id="fe378-109">Windows 서비스 응용 프로그램 소개</span><span class="sxs-lookup"><span data-stu-id="fe378-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
