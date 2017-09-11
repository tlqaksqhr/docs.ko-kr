---
title: "PrintForm 구성 요소 (Visual Basic)를 참조 하는 응용 프로그램 배포 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- PrintForm component [Visual Basic], deploying
ms.assetid: b595ea44-a712-4625-a761-190c64f59bbe
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7b625e0c58653f1ee9a2d263d7d2d29ad3b2e3c1
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="deploying-applications-that-reference-the-printform-component-visual-basic"></a><span data-ttu-id="0d5c8-102">PrintForm 구성 요소 (Visual Basic)를 참조 하는 응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="0d5c8-102">Deploying applications that reference the PrintForm component (Visual Basic)</span></span>
<span data-ttu-id="0d5c8-103">참조 하는 응용 프로그램을 배포 하려는 경우는 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>구성 요소를 대상 컴퓨터에 구성 요소를 설치 해야 합니다.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm></span><span class="sxs-lookup"><span data-stu-id="0d5c8-103">If you want to deploy an application that references the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component, the component must be installed on the destination computer.</span></span>  
  
 <span data-ttu-id="0d5c8-104">PowerPack 컨트롤은 Visual Studio에 더 포함되지 않지만 [다운로드 센터](http://www.microsoft.com/en-us/download/details.aspx?id=25169)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d5c8-104">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
## <a name="installing-the-printform-as-a-prerequisite"></a><span data-ttu-id="0d5c8-105">필수 구성 요소로 PrintForm 설치</span><span class="sxs-lookup"><span data-stu-id="0d5c8-105">Installing the PrintForm as a prerequisite</span></span>  
 <span data-ttu-id="0d5c8-106">응용 프로그램을 성공적으로 배포하려면 응용 프로그램이 참조하는 모든 구성 요소도 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d5c8-106">To successfully deploy an application, you must also deploy all components that are referenced by the application.</span></span> <span data-ttu-id="0d5c8-107">필수 조건 구성 요소를 설치하는 프로세스를 *부트스트래핑*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d5c8-107">The process of installing prerequisite components is known as *bootstrapping*.</span></span>  
  
 <span data-ttu-id="0d5c8-108">경우는 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>개발 컴퓨터에 구성 요소가 설치 되어, Microsoft Visual Basic Power Packs 부트스트래퍼 패키지에 추가 되는 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] 부트스트래퍼 디렉터리.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm></span><span class="sxs-lookup"><span data-stu-id="0d5c8-108">When the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is installed on your development computer, a Microsoft Visual Basic Power Packs bootstrapper package is added to the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] bootstrapper directory.</span></span> <span data-ttu-id="0d5c8-109">에 대 한 필수 구성 요소를 추가 하기 위한 절차를 수행 하는 경우에이 패키지는 사용할 수 있는 다음 [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] 또는 Windows Installer 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d5c8-109">This package is then available when you follow the procedures for adding prerequisites for either [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] or Windows Installer deployment.</span></span>  
  
 <span data-ttu-id="0d5c8-110">기본적으로 부트스트랩된 구성 요소는 설치 패키지와 같은 위치에서 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d5c8-110">By default, bootstrapped components are deployed from the same location as the installation package.</span></span> <span data-ttu-id="0d5c8-111">또는 사용자가 필요한 경우 다운로드할 수 있는 URL 또는 파일 공유 위치에서 구성 요소를 배포하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d5c8-111">Alternatively, you can choose to deploy the components from a URL or file share location from which users can download them as necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0d5c8-112">부트스트랩된 구성 요소를 설치하려면 사용자는 컴퓨터에서 관리 권한이나 비슷한 사용자 권한이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d5c8-112">To install bootstrapped components, the user might need administrative or similar user permissions on the computer.</span></span> <span data-ttu-id="0d5c8-113">에 대 한 [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] 응용 프로그램, 즉, 응용 프로그램에 의해 지정 된 보안 수준에 관계 없이 응용 프로그램을 설치 하려면 관리자 권한이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d5c8-113">For [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] applications, this means that the user will need administrative permissions to install the application, regardless of the security level specified by the application.</span></span> <span data-ttu-id="0d5c8-114">응용 프로그램이 설치되고 나면 사용자는 관리 권한 없이 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d5c8-114">After the application is installed, the user can run the application without administrative permissions.</span></span>  
  
 <span data-ttu-id="0d5c8-115">설치 하는 동안 메시지가 나타납니다를 설치 하는 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>구성 요소는 대상 컴퓨터에 없는 경우.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm></span><span class="sxs-lookup"><span data-stu-id="0d5c8-115">During installation, users will be prompted to install the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component if it is not present on the destination computer.</span></span>  
  
 <span data-ttu-id="0d5c8-116">부트스트래핑을 수행 하는 대신, 미리 배포할 수 있습니다는 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>Microsoft Systems Management Server와 같은 전자 소프트웨어 배포 시스템을 사용 하 여 구성 요소.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm></span><span class="sxs-lookup"><span data-stu-id="0d5c8-116">As an alternative to bootstrapping, you can pre-deploy the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component by using an electronic software distribution system like Microsoft Systems Management Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d5c8-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d5c8-117">See also</span></span>  
 <span data-ttu-id="0d5c8-118">[방법: ClickOnce 응용 프로그램 필수 구성 요소 설치](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5) </span><span class="sxs-lookup"><span data-stu-id="0d5c8-118">[How to: Install Prerequisites with a ClickOnce Application](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5) </span></span>  
<span data-ttu-id="0d5c8-119"> [PrintForm 구성 요소](../../../visual-basic/developing-apps/printing/printform-component.md)</span><span class="sxs-lookup"><span data-stu-id="0d5c8-119"> [PrintForm Component](../../../visual-basic/developing-apps/printing/printform-component.md)</span></span>
