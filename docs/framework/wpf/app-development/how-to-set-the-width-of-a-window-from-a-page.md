---
title: '방법: 페이지에서 창의 너비를 설정 합니다.'
ms.date: 03/30/2017
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
ms.openlocfilehash: a0ae0e136e0b7f1cd2a2ec56455e14723e8fa306
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545994"
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a>방법: 페이지에서 창의 너비를 설정 합니다.
창의 너비를 설정 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Page>합니다.  
  
## <a name="example"></a>예제  
 A <xref:System.Windows.Controls.Page> 설정 하 여 해당 호스트 창의 너비를 설정할 수 <xref:System.Windows.Controls.Page.WindowWidth%2A>합니다. 이 속성을 사용 하면는 <xref:System.Windows.Controls.Page> 에 없는 다음 호스팅하고 있는 창의 형식을 정확 하 게 알고 있습니다.  
  
> [!NOTE]
>  사용 하 여 창을의 너비를 설정 하려면 <xref:System.Windows.Controls.Page.WindowWidth%2A>, <xref:System.Windows.Controls.Page> 창의 자식 이어야 합니다.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
