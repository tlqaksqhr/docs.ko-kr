---
title: '방법: 페이지에서 창의 높이 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
ms.openlocfilehash: e25bc3cf2f5de01177f79f671390bac39875d079
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a>방법: 페이지에서 창의 높이 설정
창의 높이 설정 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Page>합니다.  
  
## <a name="example"></a>예제  
 A <xref:System.Windows.Controls.Page> 설정 하 여 해당 호스트 창의 높이 설정할 수 <xref:System.Windows.Controls.Page.WindowHeight%2A>합니다. 이 속성을 사용 하면는 <xref:System.Windows.Controls.Page> 에 없는 다음 호스팅하고 있는 창의 형식을 정확 하 게 알고 있습니다.  
  
> [!NOTE]
>  사용 하 여 창을의 높이 설정 하려면 <xref:System.Windows.Controls.Page.WindowHeight%2A>, <xref:System.Windows.Controls.Page> 창의 자식 이어야 합니다.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
