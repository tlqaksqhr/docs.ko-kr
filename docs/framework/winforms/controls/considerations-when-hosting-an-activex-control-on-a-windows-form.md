---
title: "Windows Form에서 ActiveX 컨트롤을 호스팅할 때의 고려 사항"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- ActiveX controls [Windows Forms], hosting
- Windows Forms, ActiveX controls
- Windows Forms, hosting ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 2509302d-a74e-484f-9890-2acdbfa67a68
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 23c8476e4013cca6d906d85f11658deddc585869
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="considerations-when-hosting-an-activex-control-on-a-windows-form"></a><span data-ttu-id="49dde-102">Windows Form에서 ActiveX 컨트롤을 호스팅할 때의 고려 사항</span><span class="sxs-lookup"><span data-stu-id="49dde-102">Considerations When Hosting an ActiveX Control on a Windows Form</span></span>
<span data-ttu-id="49dde-103">Windows Forms는 Windows Forms 컨트롤을 호스팅하도록 최적화되어 있지만 ActiveX 컨트롤을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49dde-103">Although Windows Forms have been optimized to host Windows Forms controls, you can still use ActiveX controls.</span></span> <span data-ttu-id="49dde-104">ActiveX 컨트롤을 사용하는 응용 프로그램을 계획할 때 다음 사항을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="49dde-104">Keep the following considerations in mind when planning an application that uses ActiveX controls:</span></span>  
  
-   <span data-ttu-id="49dde-105">**보안** 공용 언어 런타임이 코드 액세스 보안과 관련하여 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="49dde-105">**Security** The common language runtime has been enhanced with regard to code access security.</span></span> <span data-ttu-id="49dde-106">Windows Forms 기능이 있는 응용 프로그램은 완전히 신뢰할 수 있는 환경에서 문제 없이 실행할 수 있으며, 대부분의 기능에 액세스할 수 있지만 부분적으로 신뢰할 수 있는 환경에서도 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49dde-106">Applications featuring Windows Forms can run in a fully trusted environment without issue and in a semi-trusted environment with most of the functionality accessible.</span></span> <span data-ttu-id="49dde-107">Windows Forms 컨트롤은 브라우저에서 별다른 어려움 없이 간단하게 호스팅될 수 있지만,</span><span class="sxs-lookup"><span data-stu-id="49dde-107">Windows Forms controls can be hosted in a browser with no complications.</span></span> <span data-ttu-id="49dde-108">Windows Forms의 ActiveX 컨트롤은 향상된 보안 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49dde-108">However, ActiveX controls on Windows Forms cannot take advantage of these security enhancements.</span></span> <span data-ttu-id="49dde-109">으로 설정 된 비관리 코드 권한이 ActiveX 컨트롤을 실행 하려면는 <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="49dde-109">Running an ActiveX control requires unmanaged code permission, which is set with the <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="49dde-110">보안 및 비관리 코드 권한이 대 한 자세한 내용은 참조 <xref:System.Security.Permissions.SecurityPermissionAttribute>합니다.</span><span class="sxs-lookup"><span data-stu-id="49dde-110">For more information about security and unmanaged code permission, see <xref:System.Security.Permissions.SecurityPermissionAttribute>.</span></span>  
  
-   <span data-ttu-id="49dde-111">**TCO(총 소유 비용)** Windows Form에 추가된 ActiveX 컨트롤은 해당 Windows Form과 함께 전부 배포되므로 만들어지는 파일의 크기가 상당히 커질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49dde-111">**Total Cost of Ownership** ActiveX controls added to a Windows Form are deployed with that Windows Form in their entirety, which can add significantly to the size of the file(s) created.</span></span> <span data-ttu-id="49dde-112">또한 Windows Forms에서 ActiveX 컨트롤을 사용하려면 레지스트리에 기록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49dde-112">Additionally, using ActiveX controls on Windows Forms requires writing to the registry.</span></span> <span data-ttu-id="49dde-113">이 작업은 레지스트리에 기록할 필요가 없는 Windows Forms 컨트롤에 비해 사용자의 컴퓨터를 간섭할 여지가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="49dde-113">This is more invasive to a user's computer than Windows Forms controls, which do not require this.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="49dde-114">ActiveX 컨트롤을 사용하려면 COM interop 래퍼를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49dde-114">Working with an ActiveX control requires the use of a COM interop wrapper.</span></span> <span data-ttu-id="49dde-115">자세한 내용은 [Visual Basic 및 Visual C#의 COM 상호 운용성](~/docs/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49dde-115">For more information, see [COM Interoperability in Visual Basic and Visual C#](~/docs/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="49dde-116">ActiveX 컨트롤의 멤버의 이름에 정의 된 이름과 일치 하는 경우는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], ActiveX 컨트롤 가져오기를 사용 하 여 멤버 이름을 접두사는 다음 **Ctl** 를 만들 때의 <xref:System.Windows.Forms.AxHost> 클래스를 파생 합니다.</span><span class="sxs-lookup"><span data-stu-id="49dde-116">If the name of a member of the ActiveX control matches a name defined in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], then the ActiveX Control Importer will prefix the member name with **Ctl** when it creates the <xref:System.Windows.Forms.AxHost> derived class.</span></span> <span data-ttu-id="49dde-117">예를 들어 ActiveX 컨트롤에 **Layout**이라는 멤버가 있으면 **Layout** 이벤트가 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에 이미 정의되어 있으므로 AxHost 파생 클래스에서 이 멤버의 이름이 **CtlLayout**으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="49dde-117">For example, if your ActiveX control has a member named **Layout**, it is renamed **CtlLayout** in the AxHost-derived class because the **Layout** event is defined within the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49dde-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49dde-118">See Also</span></span>  
 [<span data-ttu-id="49dde-119">방법: Windows Forms에 ActiveX 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="49dde-119">How to: Add ActiveX Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)  
 [<span data-ttu-id="49dde-120">코드 액세스 보안</span><span class="sxs-lookup"><span data-stu-id="49dde-120">Code Access Security</span></span>](../../../../docs/framework/misc/code-access-security.md)  
 [<span data-ttu-id="49dde-121">여러 언어 및 라이브러리에서 사용되는 컨트롤 및 프로그래밍 가능한 개체 비교</span><span class="sxs-lookup"><span data-stu-id="49dde-121">Controls and Programmable Objects Compared in Various Languages and Libraries</span></span>](http://msdn.microsoft.com/library/021f2a1b-8247-4348-a5ad-e1d9ab23004b)  
 [<span data-ttu-id="49dde-122">Windows Forms에 컨트롤 넣기</span><span class="sxs-lookup"><span data-stu-id="49dde-122">Putting Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)  
 [<span data-ttu-id="49dde-123">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="49dde-123">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)
