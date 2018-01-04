---
title: "방법: 페이지에서 창의 높이 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 002e75542c1dbbe1cfaa122898801dd5babf054f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a>방법: 페이지에서 창의 높이 설정
창의 높이 설정 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Page>합니다.  
  
## <a name="example"></a>예  
 A <xref:System.Windows.Controls.Page> 설정 하 여 해당 호스트 창의 높이 설정할 수 <xref:System.Windows.Controls.Page.WindowHeight%2A>합니다. 이 속성을 사용 하면는 <xref:System.Windows.Controls.Page> 에 없는 다음 호스팅하고 있는 창의 형식을 정확 하 게 알고 있습니다.  
  
> [!NOTE]
>  사용 하 여 창을의 높이 설정 하려면 <xref:System.Windows.Controls.Page.WindowHeight%2A>, <xref:System.Windows.Controls.Page> 창의 자식 이어야 합니다.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
