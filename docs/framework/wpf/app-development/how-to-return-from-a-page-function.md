---
title: '방법: 페이지 함수에서 반환'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- returning from page functions [WPF]
- page functions [WPF], returning from
- functions [WPF], returning from
ms.assetid: 87804905-7e8f-417b-b0e3-5622da686396
ms.openlocfilehash: 3251b373b11dc7682235251b6d82e22705456737
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545514"
---
# <a name="how-to-return-from-a-page-function"></a><span data-ttu-id="f8812-102">방법: 페이지 함수에서 반환</span><span class="sxs-lookup"><span data-stu-id="f8812-102">How to: Return from a Page Function</span></span>
<span data-ttu-id="f8812-103">이 예제에서는 페이지 함수에서 결과를 반환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8812-103">This example shows how to return a result from a page function.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8812-104">예제</span><span class="sxs-lookup"><span data-stu-id="f8812-104">Example</span></span>  
 <span data-ttu-id="f8812-105">호출 해야 페이지 함수를 반환 하려면 <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> 의 인스턴스를 전달 하 고 <xref:System.Windows.Navigation.ReturnEventArgs%601>합니다.</span><span class="sxs-lookup"><span data-stu-id="f8812-105">To return from a page function, you need to call <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> and pass an instance of <xref:System.Windows.Navigation.ReturnEventArgs%601>.</span></span>  
  
 [!code-xaml[HOWTOPageFunctionSnippets#PageFunctionReturnAResultXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/GetStringPageFunction.xaml#pagefunctionreturnaresultxaml1)]  
[!code-xaml[HOWTOPageFunctionSnippets#PageFunctionReturnAResultXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/GetStringPageFunction.xaml#pagefunctionreturnaresultxaml2)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#PageFunctionReturnAResultCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/GetStringPageFunction.xaml.cs#pagefunctionreturnaresultcodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#PageFunctionReturnAResultCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/GetStringPageFunction.xaml.vb#pagefunctionreturnaresultcodebehind)]  
  
## <a name="see-also"></a><span data-ttu-id="f8812-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8812-106">See Also</span></span>  
 <xref:System.Windows.Navigation.PageFunction%601>
