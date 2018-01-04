---
title: "Windows Forms의 인쇄 추가 보안"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1f36ee150e4dcca74141b644a55451abd4a4fd21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="more-secure-printing-in-windows-forms"></a><span data-ttu-id="78826-102">Windows Forms의 인쇄 추가 보안</span><span class="sxs-lookup"><span data-stu-id="78826-102">More Secure Printing in Windows Forms</span></span>
<span data-ttu-id="78826-103">Windows Forms 응용 프로그램에 인쇄 기능이 포함 되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="78826-103">Windows Forms applications frequently include printing abilities.</span></span> <span data-ttu-id="78826-104">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 사용 하 여는 <xref:System.Drawing.Printing.PrintingPermission> 인쇄 기능에 대 한 액세스 제어 및 연결 된 클래스를 <xref:System.Drawing.Printing.PrintingPermissionLevel> 를 액세스 수준을 나타내는 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="78826-104">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] uses the <xref:System.Drawing.Printing.PrintingPermission> class to control access to printing capabilities and the associated <xref:System.Drawing.Printing.PrintingPermissionLevel> enumeration value to indicate the level of access.</span></span> <span data-ttu-id="78826-105">기본적으로 인쇄 로컬 인트라넷 및 인터넷 영역;에서 기본적으로 사용 하도록 설정 그러나 양쪽 영역에 대 한 액세스 수준이 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78826-105">By default, printing is enabled by default in the Local Intranet and Internet zones; however, the level of access is restricted in both zones.</span></span> <span data-ttu-id="78826-106">응용 프로그램 인쇄할 수 있는지, 사용자 상호 작용을 있거나 없는 응용 프로그램에 부여 된 권한 값에 따라 다릅니다 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="78826-106">Whether your application can print, requires user interaction, or cannot print depends upon the permission value granted to the application.</span></span> <span data-ttu-id="78826-107">기본적으로 로컬 인트라넷 영역 받는 <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> 액세스 및 인트라넷 영역 받는 <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="78826-107">By default, the Local Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> access and the Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> access.</span></span>  
  
 <span data-ttu-id="78826-108">다음 표에서 각 인쇄 사용 권한 수준에서 사용할 수 있는 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78826-108">The following table shows the functionality available at each printing permission level.</span></span>  
  
|<span data-ttu-id="78826-109">PrintingPermissionLevel</span><span class="sxs-lookup"><span data-stu-id="78826-109">PrintingPermissionLevel</span></span>|<span data-ttu-id="78826-110">설명</span><span class="sxs-lookup"><span data-stu-id="78826-110">Description</span></span>|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|<span data-ttu-id="78826-111">설치 된 모든 프린터에 대 한 전체 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="78826-111">Provides full access to all installed printers.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|<span data-ttu-id="78826-112">기본 프린터를 프로그래밍 방식 인쇄 및 제한적인 인쇄 대화 상자를 통해 안전 하 게 인쇄할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78826-112">Enables programmatic printing to the default printer and safer printing through a restrictive printing dialog box.</span></span> <span data-ttu-id="78826-113"><xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>는 <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>의 하위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="78826-113"><xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|<span data-ttu-id="78826-114">보다 제한 된 대화 상자 에서만에서 인쇄를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="78826-114">Provides printing only from a more-restricted dialog box.</span></span> <span data-ttu-id="78826-115"><xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>는 <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>의 하위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="78826-115"><xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|<span data-ttu-id="78826-116">프린터에 대 한 액세스를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="78826-116">Prevents access to printers.</span></span> <span data-ttu-id="78826-117"><xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>는 <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>의 하위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="78826-117"><xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78826-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78826-118">See Also</span></span>  
 [<span data-ttu-id="78826-119">Windows Forms의 파일 및 데이터 액세스 추가 보안</span><span class="sxs-lookup"><span data-stu-id="78826-119">More Secure File and Data Access in Windows Forms</span></span>](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 [<span data-ttu-id="78826-120">Windows Forms의 추가 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="78826-120">Additional Security Considerations in Windows Forms</span></span>](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 [<span data-ttu-id="78826-121">Windows Forms의 보안 개요</span><span class="sxs-lookup"><span data-stu-id="78826-121">Security in Windows Forms Overview</span></span>](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 [<span data-ttu-id="78826-122">Windows Forms 보안</span><span class="sxs-lookup"><span data-stu-id="78826-122">Windows Forms Security</span></span>](../../../docs/framework/winforms/windows-forms-security.md)
