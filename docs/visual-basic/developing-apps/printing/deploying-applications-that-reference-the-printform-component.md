---
title: "PrintForm 구성 요소 (Visual Basic)를 참조 하는 응용 프로그램 배포"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: PrintForm component [Visual Basic], deploying
ms.assetid: b595ea44-a712-4625-a761-190c64f59bbe
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 15b6e21e769c90e23e66e4f87b37f74462423985
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="deploying-applications-that-reference-the-printform-component-visual-basic"></a><span data-ttu-id="5e184-102">PrintForm 구성 요소 (Visual Basic)를 참조 하는 응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="5e184-102">Deploying applications that reference the PrintForm component (Visual Basic)</span></span>
<span data-ttu-id="5e184-103"><xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소를 참조하는 응용 프로그램을 배포하려면 대상 컴퓨터에 구성 요소를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e184-103">If you want to deploy an application that references the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component, the component must be installed on the destination computer.</span></span>  
  
 <span data-ttu-id="5e184-104">PowerPack 컨트롤은 Visual Studio에 더 포함되지 않지만 [다운로드 센터](http://www.microsoft.com/en-us/download/details.aspx?id=25169)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e184-104">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
## <a name="installing-the-printform-as-a-prerequisite"></a><span data-ttu-id="5e184-105">PrintForm을 필수 조건으로 설치</span><span class="sxs-lookup"><span data-stu-id="5e184-105">Installing the PrintForm as a prerequisite</span></span>  
 <span data-ttu-id="5e184-106">응용 프로그램을 성공적으로 배포하려면 응용 프로그램이 참조하는 모든 구성 요소도 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e184-106">To successfully deploy an application, you must also deploy all components that are referenced by the application.</span></span> <span data-ttu-id="5e184-107">필수 조건 구성 요소를 설치하는 프로세스를 *부트스트래핑*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e184-107">The process of installing prerequisite components is known as *bootstrapping*.</span></span>  
  
 <span data-ttu-id="5e184-108"><xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소가 개발 컴퓨터에 설치될 때 Microsoft Visual Basic Power Packs 부트스트래퍼 패키지가 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 부트스트래퍼 디렉터리에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e184-108">When the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is installed on your development computer, a Microsoft Visual Basic Power Packs bootstrapper package is added to the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] bootstrapper directory.</span></span> <span data-ttu-id="5e184-109">이 패키지는 [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] 또는 Windows Installer 배포에 대한 필수 조건을 추가하는 절차를 수행할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e184-109">This package is then available when you follow the procedures for adding prerequisites for either [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] or Windows Installer deployment.</span></span>  
  
 <span data-ttu-id="5e184-110">기본적으로 부트스트랩된 구성 요소는 설치 패키지와 같은 위치에서 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e184-110">By default, bootstrapped components are deployed from the same location as the installation package.</span></span> <span data-ttu-id="5e184-111">또는 사용자가 필요한 경우 다운로드할 수 있는 URL 또는 파일 공유 위치에서 구성 요소를 배포하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e184-111">Alternatively, you can choose to deploy the components from a URL or file share location from which users can download them as necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e184-112">부트스트랩된 구성 요소를 설치하려면 사용자는 컴퓨터에서 관리 권한이나 비슷한 사용자 권한이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e184-112">To install bootstrapped components, the user might need administrative or similar user permissions on the computer.</span></span> <span data-ttu-id="5e184-113">[!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] 응용 프로그램의 경우 이는 응용 프로그램에서 지정된 보안 수준과 관계없이 응용 프로그램을 설치할 관리 권한이 사용자에게 필요함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="5e184-113">For [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] applications, this means that the user will need administrative permissions to install the application, regardless of the security level specified by the application.</span></span> <span data-ttu-id="5e184-114">응용 프로그램이 설치되고 나면 사용자는 관리 권한 없이 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e184-114">After the application is installed, the user can run the application without administrative permissions.</span></span>  
  
 <span data-ttu-id="5e184-115">설치하는 동안 대상 컴퓨터에 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소가 없을 경우 해당 구성 요소를 설치할지 묻는 메시지가 사용자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e184-115">During installation, users will be prompted to install the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component if it is not present on the destination computer.</span></span>  
  
 <span data-ttu-id="5e184-116">부트스트래핑 대신 Microsoft Systems Management Server와 같은 전자 소프트웨어 배포 시스템을 사용하여 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소를 미리 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e184-116">As an alternative to bootstrapping, you can pre-deploy the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component by using an electronic software distribution system like Microsoft Systems Management Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e184-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5e184-117">See also</span></span>  
 [<span data-ttu-id="5e184-118">방법: ClickOnce 응용 프로그램을 사용하여 필수 조건 설치</span><span class="sxs-lookup"><span data-stu-id="5e184-118">How to: Install Prerequisites with a ClickOnce Application</span></span>](/visualstudio/deployment/how-to-install-prerequisites-with-a-clickonce-application)  
 [<span data-ttu-id="5e184-119">PrintForm 구성 요소</span><span class="sxs-lookup"><span data-stu-id="5e184-119">PrintForm Component</span></span>](../../../visual-basic/developing-apps/printing/printform-component.md)
