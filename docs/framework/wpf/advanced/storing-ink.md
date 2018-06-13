---
title: 잉크 저장
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ISF (Ink Serialized Format)
- storing ink [WPF]
- ink [WPF], storing
- retrieving ink [WPF]
- Ink Serialized Format (ISF)
ms.assetid: a3f6d16b-d682-4680-9965-907332b4d2b8
ms.openlocfilehash: d3d33be5e8b5cf9dd7e32a52dfc258aa934c5c11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546099"
---
# <a name="storing-ink"></a><span data-ttu-id="58e8a-102">잉크 저장</span><span class="sxs-lookup"><span data-stu-id="58e8a-102">Storing Ink</span></span>
<span data-ttu-id="58e8a-103"><xref:System.Windows.Ink.StrokeCollection.Save%2A> 메서드 잉크도 잉크 직렬화 형식 ISF ()를 저장 하기 위한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e8a-103">The <xref:System.Windows.Ink.StrokeCollection.Save%2A> methods provide support for storing ink as Ink Serialized Format (ISF).</span></span> <span data-ttu-id="58e8a-104">에 대 한 생성자는 <xref:System.Windows.Ink.StrokeCollection> 클래스 잉크 데이터를 읽기 위한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e8a-104">Constructors for the <xref:System.Windows.Ink.StrokeCollection> class provide support for reading ink data.</span></span>  
  
## <a name="ink-storage-and-retrieval"></a><span data-ttu-id="58e8a-105">잉크 저장 및 검색</span><span class="sxs-lookup"><span data-stu-id="58e8a-105">Ink Storage and Retrieval</span></span>  
 <span data-ttu-id="58e8a-106">이 섹션에서는 저장 하 고에 잉크를 검색 하는 방법을 설명의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="58e8a-106">This section discusses how to store and retrieve ink in the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] platform.</span></span>  
  
 <span data-ttu-id="58e8a-107">다음 예제에서는 구현 파일 저장 대화 상자에 있는 사용자에 게 표시 하 고에서 잉크를 저장 하는 단추 클릭 이벤트 처리기는 <xref:System.Windows.Controls.InkCanvas> 를 파일로 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e8a-107">The following example implements a button-click event handler that presents the user with a File Save dialog box and saves the ink from an <xref:System.Windows.Controls.InkCanvas> out to a file.</span></span>  
  
 [!code-csharp[DigitalInkTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#12)]
 [!code-vb[DigitalInkTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#12)]  
  
 <span data-ttu-id="58e8a-108">다음 예제에서는 잉크에이 파일에서 읽고 파일 열기 대화 상자에 있는 사용자에 게 표시 단추 클릭 이벤트 처리기를 구현 하는 <xref:System.Windows.Controls.InkCanvas> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58e8a-108">The following example implements a button-click event handler that presents the user with a File Open dialog box and reads ink from the file into an <xref:System.Windows.Controls.InkCanvas> element.</span></span>  
  
 [!code-csharp[DigitalInkTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#13)]
 [!code-vb[DigitalInkTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="58e8a-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58e8a-109">See Also</span></span>  
 <xref:System.Windows.Controls.InkCanvas>  
 [<span data-ttu-id="58e8a-110">Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="58e8a-110">Windows Presentation Foundation</span></span>](../../../../docs/framework/wpf/index.md)
