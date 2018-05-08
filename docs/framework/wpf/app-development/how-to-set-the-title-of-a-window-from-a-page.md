---
title: '방법: 페이지에서 창의 제목 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
ms.openlocfilehash: e69812b59783717b7b9c832d4e8ab01ab42827c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a>방법: 페이지에서 창의 제목 설정
창의 제목이를 설정 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Page> 호스팅됩니다.  
  
## <a name="example"></a>예제  
 페이지를 설정 하 여 호스팅하는 창 제목을 변경할 수는 <xref:System.Windows.Controls.Page.WindowTitle%2A> 속성을 다음과 같이 합니다.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
>  설정의 <xref:System.Windows.Controls.Page.Title%2A> 페이지의 속성 창 제목의 값을 변경 되지 않습니다. 대신, <xref:System.Windows.Controls.Page.Title%2A> 탐색 기록에서 페이지 항목의 이름을 지정 합니다.
