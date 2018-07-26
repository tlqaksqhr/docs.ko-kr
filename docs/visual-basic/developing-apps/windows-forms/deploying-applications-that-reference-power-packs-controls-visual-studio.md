---
title: Power Packs 컨트롤 (Visual Studio)를 참조 하는 응용 프로그램 배포
ms.date: 07/20/2015
helpviewer_keywords:
- Power Packs, deploying
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
ms.openlocfilehash: bd235bc0b4a7f9978333931ae1dce012c0950374
ms.sourcegitcommit: 2d8b7488d94101b534ca3e9780b1c1e840233405
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39198230"
---
# <a name="deploying-applications-that-reference-power-packs-controls-visual-studio"></a><span data-ttu-id="a0a95-102">Power Packs 컨트롤 (Visual Studio)를 참조 하는 응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="a0a95-102">Deploying applications that reference Power Packs controls (Visual Studio)</span></span>
<span data-ttu-id="a0a95-103">Power Packs 컨트롤을 참조 하는 응용 프로그램을 배포 하려는 경우 (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>를 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, 또는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), 대상 컴퓨터의 컨트롤을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a95-103">If you want to deploy an application that references the Power Packs controls (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, or <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), the controls must be installed on the destination computer.</span></span>  
  
## <a name="installing-the-power-packs-controls-as-a-prerequisite"></a><span data-ttu-id="a0a95-104">Power Packs 컨트롤의 필수 구성 요소로 설치</span><span class="sxs-lookup"><span data-stu-id="a0a95-104">Installing the Power Packs controls as a prerequisite</span></span>  
 <span data-ttu-id="a0a95-105">응용 프로그램을 성공적으로 배포하려면 응용 프로그램이 참조하는 모든 구성 요소도 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a95-105">To successfully deploy an application, you must also deploy all components that are referenced by the application.</span></span> <span data-ttu-id="a0a95-106">필수 조건 구성 요소를 설치하는 프로세스를 *부트스트래핑*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a95-106">The process of installing prerequisite components is known as *bootstrapping*.</span></span>  
  
 <span data-ttu-id="a0a95-107">Visual Studio는 개발 컴퓨터에 설치 하는 경우 Power Packs 부트스트래퍼 패키지가 Visual Studio 부트스트래퍼 디렉터리에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0a95-107">When Visual Studio is installed on your development computer, a Power Packs bootstrapper package is added to the Visual Studio bootstrapper directory.</span></span> <span data-ttu-id="a0a95-108">이 패키지는 [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] 또는 Windows Installer 배포에 대한 필수 조건을 추가하는 절차를 수행할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a95-108">This package is then available when you follow the procedures for adding prerequisites for either [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] or Windows Installer deployment.</span></span>  
  
 <span data-ttu-id="a0a95-109">기본적으로 부트스트랩된 구성 요소는 설치 패키지와 같은 위치에서 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0a95-109">By default, bootstrapped components are deployed from the same location as the installation package.</span></span> <span data-ttu-id="a0a95-110">또는 사용자가 필요한 경우 다운로드할 수 있는 URL 또는 파일 공유 위치에서 구성 요소를 배포하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a95-110">Alternatively, you can choose to deploy the components from a URL or file share location from which users can download them as necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0a95-111">부트스트랩된 구성 요소를 설치하려면 사용자는 컴퓨터에서 관리 권한이나 비슷한 사용자 권한이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a95-111">To install bootstrapped components, the user might need administrative or similar user permissions on the computer.</span></span> <span data-ttu-id="a0a95-112">[!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] 응용 프로그램의 경우 이는 응용 프로그램에서 지정된 보안 수준과 관계없이 응용 프로그램을 설치할 관리 권한이 사용자에게 필요함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a95-112">For [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] applications, this means that the user will need administrative permissions to install the application, regardless of the security level specified by the application.</span></span> <span data-ttu-id="a0a95-113">응용 프로그램이 설치되고 나면 사용자는 관리 권한 없이 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a95-113">After the application is installed, the user can run the application without administrative permissions.</span></span>  
  
 <span data-ttu-id="a0a95-114">설치 하는 동안 사용자 대상 컴퓨터에 없는 경우 Power Packs 컨트롤을 설치 하 라는 메시지가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0a95-114">During installation, users will be prompted to install the Power Packs controls if they are not present on the destination computer.</span></span>  
  
 <span data-ttu-id="a0a95-115">부트스트래핑 대신 Microsoft Systems Management Server와 같은 전자적 소프트웨어 배포 시스템을 사용 하 여 Power Packs 컨트롤을 미리 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a95-115">As an alternative to bootstrapping, you can pre-deploy the Power Packs controls by using an electronic software distribution system such as Microsoft Systems Management Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0a95-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="a0a95-116">See also</span></span>  
 [<span data-ttu-id="a0a95-117">방법: ClickOnce 응용 프로그램을 사용하여 필수 조건 설치</span><span class="sxs-lookup"><span data-stu-id="a0a95-117">How to: Install Prerequisites with a ClickOnce Application</span></span>](/visualstudio/deployment/how-to-install-prerequisites-with-a-clickonce-application)  
 [<span data-ttu-id="a0a95-118">Visual Basic Power Packs 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a0a95-118">Visual Basic Power Packs Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)
