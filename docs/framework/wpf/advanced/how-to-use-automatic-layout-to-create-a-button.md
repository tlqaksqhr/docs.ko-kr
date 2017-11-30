---
title: "방법: 자동 레이아웃을 사용하여 단추 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7d55dc1330c21e7eb9f7cfd7f554234dccd6f274
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a><span data-ttu-id="d3a61-102">방법: 자동 레이아웃을 사용하여 단추 만들기</span><span class="sxs-lookup"><span data-stu-id="d3a61-102">How to: Use Automatic Layout to Create a Button</span></span>
<span data-ttu-id="d3a61-103">이 예제는 자동 레이아웃 방식을 사용하여 지역화 가능한 응용 프로그램에 단추를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a61-103">This example describes how to use the automatic layout approach to create a button in a localizable application.</span></span>  
  
 <span data-ttu-id="d3a61-104">지역화 된 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 많은 시간이 소요 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3a61-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="d3a61-105">종종 지역화 담당자는 텍스트 번역 외에도 요소 크기를 조정하고 위치를 재조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a61-105">Often localizers need to resize and reposition elements in addition to translating text.</span></span> <span data-ttu-id="d3a61-106">이전에는 각 언어는는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 가 조정 작업이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a61-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="d3a61-107">기능으로 이제 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 조정 사용할 필요성이 감소 하는 요소를 디자인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3a61-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="d3a61-108">보다 쉽게 크기 및 위치가 변경 될 수 있는 응용 프로그램을 작성 하는 방법을 라고 `automatic layout`합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a61-108">The approach to writing applications that can be more easily resized and repositioned is called `automatic layout`.</span></span>  
  
 <span data-ttu-id="d3a61-109">다음 두 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 예제에서는 단추; 영어 텍스트 한와 스페인어 텍스트를 인스턴스화하는 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3a61-109">The following two [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples create applications that instantiate a button; one with English text and one with Spanish text.</span></span> <span data-ttu-id="d3a61-110">코드는 텍스트를 제외하고 동일합니다. 단추는 텍스트에 맞게 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3a61-110">Notice that the code is the same except for the text; the button adjusts to fit the text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3a61-111">예제</span><span class="sxs-lookup"><span data-stu-id="d3a61-111">Example</span></span>  
 [!code-xaml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 [!code-xaml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="d3a61-112">다음 그림에서는 코드 샘플의 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3a61-112">The following graphic shows the output of the code samples.</span></span>  
  
 <span data-ttu-id="d3a61-113">![다른 언어로 된 텍스트는 동일한 단추](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")</span><span class="sxs-lookup"><span data-stu-id="d3a61-113">![The same button with text in different languages](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")</span></span>  
<span data-ttu-id="d3a61-114">자동 크기 조정 단추</span><span class="sxs-lookup"><span data-stu-id="d3a61-114">Auto Resizable Button</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3a61-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3a61-115">See Also</span></span>  
 [<span data-ttu-id="d3a61-116">자동 레이아웃 사용 개요</span><span class="sxs-lookup"><span data-stu-id="d3a61-116">Use Automatic Layout Overview</span></span>](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)  
 [<span data-ttu-id="d3a61-117">자동 레이아웃에 그리드 사용</span><span class="sxs-lookup"><span data-stu-id="d3a61-117">Use a Grid for Automatic Layout</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)
