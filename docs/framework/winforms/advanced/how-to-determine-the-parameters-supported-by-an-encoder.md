---
title: "방법: 인코더에서 지원하는 매개 변수 확인"
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
helpviewer_keywords: encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3304adc9ab22d12905bd2a6c3739d909387d82cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a><span data-ttu-id="4f8e9-102">방법: 인코더에서 지원하는 매개 변수 확인</span><span class="sxs-lookup"><span data-stu-id="4f8e9-102">How to: Determine the Parameters Supported by an Encoder</span></span>
<span data-ttu-id="4f8e9-103">품질 및 압축 수준 등의 이미지 매개 변수를 조정할 수 있지만 지정된 이미지 인코더에 의해 지원 되는 매개 변수를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f8e9-103">You can adjust image parameters, such as quality and compression level, but you must know which parameters are supported by a given image encoder.</span></span> <span data-ttu-id="4f8e9-104"><xref:System.Drawing.Image> 클래스를 제공는 <xref:System.Drawing.Image.GetEncoderParameterList%2A> 메서드를 특정 인코더에 대 한 지원 되는 이미지 매개 변수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f8e9-104">The <xref:System.Drawing.Image> class provides the <xref:System.Drawing.Image.GetEncoderParameterList%2A> method so that you can determine which image parameters are supported for a particular encoder.</span></span> <span data-ttu-id="4f8e9-105">GUID가 하는 인코더를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f8e9-105">You specify the encoder with a GUID.</span></span> <span data-ttu-id="4f8e9-106"><xref:System.Drawing.Image.GetEncoderParameterList%2A> 메서드 배열을 반환 <xref:System.Drawing.Imaging.EncoderParameter> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4f8e9-106">The <xref:System.Drawing.Image.GetEncoderParameterList%2A> method returns an array of <xref:System.Drawing.Imaging.EncoderParameter> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f8e9-107">예</span><span class="sxs-lookup"><span data-stu-id="4f8e9-107">Example</span></span>  
 <span data-ttu-id="4f8e9-108">다음 예제 코드는 JPEG 인코더에 대 한 지원 되는 매개 변수를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="4f8e9-108">The following example code outputs the supported parameters for the JPEG encoder.</span></span> <span data-ttu-id="4f8e9-109">매개 변수 범주 및 연관 된 Guid의 목록을 사용 하 여는 <xref:System.Drawing.Imaging.Encoder> 클래스 개요 각 매개 변수에 대 한 범주를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f8e9-109">Use the list of parameter categories and associated GUIDs in the <xref:System.Drawing.Imaging.Encoder> class overview to determine the category for each parameter.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4f8e9-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="4f8e9-110">Compiling the Code</span></span>  
 <span data-ttu-id="4f8e9-111">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4f8e9-111">This example requires:</span></span>  
  
-   <span data-ttu-id="4f8e9-112">Windows Forms 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="4f8e9-112">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="4f8e9-113">A <xref:System.Windows.Forms.PaintEventArgs>의 매개 변수인 <xref:System.Windows.Forms.PaintEventHandler>합니다.</span><span class="sxs-lookup"><span data-stu-id="4f8e9-113">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f8e9-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f8e9-114">See Also</span></span>  
 [<span data-ttu-id="4f8e9-115">방법: 설치된 인코더 나열</span><span class="sxs-lookup"><span data-stu-id="4f8e9-115">How to: List Installed Encoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [<span data-ttu-id="4f8e9-116">비트맵의 유형</span><span class="sxs-lookup"><span data-stu-id="4f8e9-116">Types of Bitmaps</span></span>](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)  
 [<span data-ttu-id="4f8e9-117">관리되는 GDI+에서 이미지 인코더 및 디코더 사용</span><span class="sxs-lookup"><span data-stu-id="4f8e9-117">Using Image Encoders and Decoders in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
