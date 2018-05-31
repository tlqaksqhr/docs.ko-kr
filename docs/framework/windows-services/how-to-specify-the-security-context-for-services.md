---
title: '방법: 서비스에 대한 보안 컨텍스트 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, security
- security [Visual Studio], contexts
- contexts, Visual Studio security
- security [Visual Studio], service applications
- ServiceProcessInstaller class, security context
- services, security
- ServiceInstaller class, security context
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
author: ghogen
manager: douge
ms.openlocfilehash: e3e5ad7dd44dcaf1593ac80bbe6d0a367964e4e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512478"
---
# <a name="how-to-specify-the-security-context-for-services"></a><span data-ttu-id="96515-102">방법: 서비스에 대한 보안 컨텍스트 지정</span><span class="sxs-lookup"><span data-stu-id="96515-102">How to: Specify the Security Context for Services</span></span>
<span data-ttu-id="96515-103">기본적으로 서비스는 로그인한 사용자와 다른 보안 컨텍스트에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="96515-103">By default, services run in a different security context than that of the logged-in user.</span></span> <span data-ttu-id="96515-104">서비스는 기본 시스템 계정 `LocalSystem`의 컨텍스트에서 실행되므로, 시스템 리소스에 대해 사용자와는 다른 액세스 권한을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="96515-104">Services run in the context of the default system account, called `LocalSystem`, which gives them different access privileges to system resources than the user.</span></span> <span data-ttu-id="96515-105">이 동작을 변경하여 서비스를 실행할 다른 사용자 계정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96515-105">You can change this behavior to specify a different user account under which your service should run.</span></span>  
  
 <span data-ttu-id="96515-106">보안 컨텍스트는 서비스가 실행되는 프로세스에 대한 <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> 속성을 조작하여 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="96515-106">You set the security context by manipulating the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property for the process within which the service runs.</span></span> <span data-ttu-id="96515-107">이 속성을 사용하면 서비스를 다음 네 가지 계정 유형 중 하나로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96515-107">This property allows you to set the service to one of four account types:</span></span>  
  
-   <span data-ttu-id="96515-108">`User` - 네트워크의 단일 사용자가 지정한 계정의 컨텐스트에서 서비스가 설치 및 실행될 때 시스템에서 유효한 사용자 이름과 암호를 묻는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="96515-108">`User`, which causes the system to prompt for a valid user name and password when the service is installed and runs in the context of an account specified by a single user on the network;</span></span>  
  
-   <span data-ttu-id="96515-109">`LocalService` - 로컬 컴퓨터에서 권한 없는 사용자의 역할을 하며 원격 서버에 익명 자격 증명을 제공하는 계정의 컨텍스트에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="96515-109">`LocalService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents anonymous credentials to any remote server;</span></span>  
  
-   <span data-ttu-id="96515-110">`LocalSystem` - 광범위한 로컬 권한을 제공하며 원격 서버에 컴퓨터의 자격 증명을 제공하는 계정의 컨텍스트에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="96515-110">`LocalSystem`, which runs in the context of an account that provides extensive local privileges, and presents the computer's credentials to any remote server;</span></span>  
  
-   <span data-ttu-id="96515-111">`NetworkService` - 로컬 컴퓨터에서 권한 없는 사용자 역할을 하며 원격 서버에 컴퓨터의 자격 증명을 제공하는 계정의 컨텍스트에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="96515-111">`NetworkService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents the computer's credentials to any remote server.</span></span>  
  
 <span data-ttu-id="96515-112">자세한 내용은 <xref:System.ServiceProcess.ServiceAccount> 열거형을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96515-112">For more information, see the <xref:System.ServiceProcess.ServiceAccount> enumeration.</span></span>  
  
### <a name="to-specify-the-security-context-for-a-service"></a><span data-ttu-id="96515-113">서비스에 대한 보안 컨텍스트를 지정하려면</span><span class="sxs-lookup"><span data-stu-id="96515-113">To specify the security context for a service</span></span>  
  
1.  <span data-ttu-id="96515-114">서비스를 만든 후 서비스에 필요한 설치 관리자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="96515-114">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="96515-115">자세한 내용은 [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)(방법: 서비스 응용 프로그램에 설치 관리자 추가)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96515-115">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
2.  <span data-ttu-id="96515-116">디자이너에서 `ProjectInstaller` 클래스에 액세스하고 작업 중인 서비스에 대한 서비스 프로세스 설치 관리자를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="96515-116">In the designer, access the `ProjectInstaller` class and click the service process installer for the service you are working with.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="96515-117">모든 서비스 응용 프로그램의 `ProjectInstaller` 클래스에는 적어도 두 개의 설치 구성 요소가 있는데, 프로젝트의 모든 서비스에 대한 프로세스를 설치하는 구성 요소와 응용 프로그램에 포함된 각 서비스에 대한 설치 관리자 1개입니다.</span><span class="sxs-lookup"><span data-stu-id="96515-117">For every service application, there are at least two installation components in the `ProjectInstaller` class — one that installs the processes for all services in the project, and one installer for each service the application contains.</span></span> <span data-ttu-id="96515-118">이 인스턴스에서 <xref:System.ServiceProcess.ServiceProcessInstaller>을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96515-118">In this instance, you want to select <xref:System.ServiceProcess.ServiceProcessInstaller>.</span></span>  
  
3.  <span data-ttu-id="96515-119">**속성** 창에서 <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A>를 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="96515-119">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> to the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96515-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96515-120">See Also</span></span>  
 [<span data-ttu-id="96515-121">Windows 서비스 응용 프로그램 소개</span><span class="sxs-lookup"><span data-stu-id="96515-121">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="96515-122">방법: 서비스 응용 프로그램에 설치 관리자 추가</span><span class="sxs-lookup"><span data-stu-id="96515-122">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="96515-123">방법: Windows 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="96515-123">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)
