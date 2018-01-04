---
title: "GDI+의 메타파일"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2b9d378f82b2a7edca00fedaacdcc0fca179c5a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="metafiles-in-gdi"></a><span data-ttu-id="dfe87-102">GDI+의 메타파일</span><span class="sxs-lookup"><span data-stu-id="dfe87-102">Metafiles in GDI+</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="dfe87-103">제공 된 <xref:System.Drawing.Imaging.Metafile> 클래스를 기록 하 고 메타 파일을 표시할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfe87-103"> provides the <xref:System.Drawing.Imaging.Metafile> class so that you can record and display metafiles.</span></span> <span data-ttu-id="dfe87-104">벡터 이미지 라고도 불리는 메타 파일 그리기 명령 및 설정의 시퀀스로 저장 되는 이미지를입니다.</span><span class="sxs-lookup"><span data-stu-id="dfe87-104">A metafile, also called a vector image, is an image that is stored as a sequence of drawing commands and settings.</span></span> <span data-ttu-id="dfe87-105">명령 및 설정에 기록 된 <xref:System.Drawing.Imaging.Metafile> 개체를 메모리에 저장 되거나를 파일이 나 스트림에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfe87-105">The commands and settings recorded in a <xref:System.Drawing.Imaging.Metafile> object can be stored in memory or saved to a file or stream.</span></span>  
  
## <a name="metafile-formats"></a><span data-ttu-id="dfe87-106">메타 파일 형식</span><span class="sxs-lookup"><span data-stu-id="dfe87-106">Metafile Formats</span></span>  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="dfe87-107">다음 형식으로 저장 된 메타 파일을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfe87-107"> can display metafiles that have been stored in the following formats:</span></span>  
  
-   <span data-ttu-id="dfe87-108">Windows 메타 파일 WMF)</span><span class="sxs-lookup"><span data-stu-id="dfe87-108">Windows Metafile (WMF)</span></span>  
  
-   <span data-ttu-id="dfe87-109">EMF(확장 메타파일)</span><span class="sxs-lookup"><span data-stu-id="dfe87-109">Enhanced Metafile (EMF)</span></span>  
  
-   <span data-ttu-id="dfe87-110">EMF +</span><span class="sxs-lookup"><span data-stu-id="dfe87-110">EMF+</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="dfe87-111">WMF 형식의 있지만 EMF 및 EMF + 형식에 메타 파일을 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfe87-111"> can record metafiles in the EMF and EMF+ formats, but not in the WMF format.</span></span>  
  
 <span data-ttu-id="dfe87-112">EMF +는 emf 수 있는 확장 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 레코드를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfe87-112">EMF+ is an extension to EMF that allows [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] records to be stored.</span></span> <span data-ttu-id="dfe87-113">EMF + 형식에 두 가지 변형이 있습니다: 및 EMF + 복합 EMF +만 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfe87-113">There are two variations on the EMF+ format: EMF+ Only and EMF+ Dual.</span></span> <span data-ttu-id="dfe87-114">메타 파일 EMF +만 포함 될 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="dfe87-114">EMF+ Only metafiles contain only [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] records.</span></span> <span data-ttu-id="dfe87-115">이러한 메타 파일은 표시할 수 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 하지만 하지 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="dfe87-115">Such metafiles can be displayed by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] but not by [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span> <span data-ttu-id="dfe87-116">EMF + 복합 메타 파일 포함 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 및 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="dfe87-116">EMF+ Dual metafiles contain [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] records.</span></span> <span data-ttu-id="dfe87-117">각 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 레코드 EMF + 복합에 메타 파일 쌍을 이룹니다 대체 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="dfe87-117">Each [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] record in an EMF+ Dual metafile is paired with an alternate [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] record.</span></span> <span data-ttu-id="dfe87-118">이러한 메타 파일은 표시할 수 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 또는 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="dfe87-118">Such metafiles can be displayed by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] or by [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 <span data-ttu-id="dfe87-119">다음 예제에서는 이전에 파일로 저장 된 메타 파일을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfe87-119">The following example displays a metafile that was previously saved as a file.</span></span> <span data-ttu-id="dfe87-120">메타 파일은 왼쪽 위 모퉁이 표시 됩니다 (100, 100).</span><span class="sxs-lookup"><span data-stu-id="dfe87-120">The metafile is displayed with its upper-left corner at (100, 100).</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="dfe87-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dfe87-121">See Also</span></span>  
 [<span data-ttu-id="dfe87-122">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="dfe87-122">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
