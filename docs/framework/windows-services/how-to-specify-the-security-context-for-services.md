---
title: "방법: 서비스에 대한 보안 컨텍스트 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, security
- security [Visual Studio], contexts
- contexts, Visual Studio security
- security [Visual Studio], service applications
- ServiceProcessInstaller class, security context
- services, security
- ServiceInstaller class, security context
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
caps.latest.revision: "10"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 9ce65358f6d63414dbe6798d3cc2464ee2741980
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-the-security-context-for-services"></a><span data-ttu-id="277ae-102">방법: 서비스에 대한 보안 컨텍스트 지정</span><span class="sxs-lookup"><span data-stu-id="277ae-102">How to: Specify the Security Context for Services</span></span>
<span data-ttu-id="277ae-103">기본적으로 서비스에 로그인 한 사용자의 다른 보안 컨텍스트에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="277ae-103">By default, services run in a different security context than that of the logged-in user.</span></span> <span data-ttu-id="277ae-104">기본 시스템 계정의 컨텍스트에서 실행 되는 서비스 호출 `LocalSystem`는 서로 다른 액세스 권한을 부여 시스템 리소스에는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="277ae-104">Services run in the context of the default system account, called `LocalSystem`, which gives them different access privileges to system resources than the user.</span></span> <span data-ttu-id="277ae-105">서비스 실행 해야 하는 다른 사용자 계정을 지정 하려면이 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="277ae-105">You can change this behavior to specify a different user account under which your service should run.</span></span>  
  
 <span data-ttu-id="277ae-106">조작 하 여 보안 컨텍스트를 설정한는 <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> 서비스가 실행 되는 프로세스에 대 한 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="277ae-106">You set the security context by manipulating the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property for the process within which the service runs.</span></span> <span data-ttu-id="277ae-107">이 속성을 사용 하면 서비스 네 가지 계정 형식 중 하나로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="277ae-107">This property allows you to set the service to one of four account types:</span></span>  
  
-   <span data-ttu-id="277ae-108">`User`이 경우 서비스 설치 하는 네트워크에서 단일 사용자가 지정한 계정의 컨텍스트에서 실행 될 때 유효한 사용자 이름 및 암호에 대 한 메시지를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="277ae-108">`User`, which causes the system to prompt for a valid user name and password when the service is installed and runs in the context of an account specified by a single user on the network;</span></span>  
  
-   <span data-ttu-id="277ae-109">`LocalService`를 로컬 컴퓨터에서 권한 없는 사용자의 역할을 하 고; 원격 서버에 익명 자격 증명을 제공 하는 계정의 컨텍스트에서 실행 되는</span><span class="sxs-lookup"><span data-stu-id="277ae-109">`LocalService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents anonymous credentials to any remote server;</span></span>  
  
-   <span data-ttu-id="277ae-110">`LocalSystem`광범위 한 로컬 권한을 제공 하 고 원격 서버로; 컴퓨터의 자격 증명을 제공 하는 계정의 컨텍스트에서 실행 되는</span><span class="sxs-lookup"><span data-stu-id="277ae-110">`LocalSystem`, which runs in the context of an account that provides extensive local privileges, and presents the computer's credentials to any remote server;</span></span>  
  
-   <span data-ttu-id="277ae-111">`NetworkService`를 로컬 컴퓨터에서 권한 없는 사용자의 역할을 원격 서버에 컴퓨터의 자격 증명을 제공 하는 계정의 컨텍스트에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="277ae-111">`NetworkService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents the computer's credentials to any remote server.</span></span>  
  
 <span data-ttu-id="277ae-112">자세한 내용은 <xref:System.ServiceProcess.ServiceAccount> 열거형을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="277ae-112">For more information, see the <xref:System.ServiceProcess.ServiceAccount> enumeration.</span></span>  
  
### <a name="to-specify-the-security-context-for-a-service"></a><span data-ttu-id="277ae-113">서비스에 대 한 보안 컨텍스트를 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="277ae-113">To specify the security context for a service</span></span>  
  
1.  <span data-ttu-id="277ae-114">서비스를 만든 후에 필요한 설치 관리자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="277ae-114">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="277ae-115">자세한 내용은 참조 [하는 방법: 서비스 응용 프로그램 설치 관리자 추가](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="277ae-115">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
2.  <span data-ttu-id="277ae-116">디자이너에서 액세스는 `ProjectInstaller` 클래스 하 고 사용 하는 서비스에 대 한 서비스 프로세스 설치 관리자를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="277ae-116">In the designer, access the `ProjectInstaller` class and click the service process installer for the service you are working with.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="277ae-117">모든 서비스 응용 프로그램에 대 한는에서 두 개 이상 설치 구성 요소는 `ProjectInstaller` 클래스-모든 서비스에 대 한 프로세스는 프로젝트 및 응용 프로그램을 포함 하는 각 서비스에 대해 한 명의 설치 관리자에서 설치 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="277ae-117">For every service application, there are at least two installation components in the `ProjectInstaller` class — one that installs the processes for all services in the project, and one installer for each service the application contains.</span></span> <span data-ttu-id="277ae-118">이 경우에 선택 하려는 <xref:System.ServiceProcess.ServiceProcessInstaller>합니다.</span><span class="sxs-lookup"><span data-stu-id="277ae-118">In this instance, you want to select <xref:System.ServiceProcess.ServiceProcessInstaller>.</span></span>  
  
3.  <span data-ttu-id="277ae-119">에 **속성** 창에서 설정 된 <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> 적절 한 값으로.</span><span class="sxs-lookup"><span data-stu-id="277ae-119">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> to the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="277ae-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="277ae-120">See Also</span></span>  
 [<span data-ttu-id="277ae-121">Windows 서비스 응용 프로그램 소개</span><span class="sxs-lookup"><span data-stu-id="277ae-121">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="277ae-122">방법: 서비스 응용 프로그램에 설치 관리자 추가</span><span class="sxs-lookup"><span data-stu-id="277ae-122">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="277ae-123">방법: Windows 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="277ae-123">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)
