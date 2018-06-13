---
title: '방법: GruopBox 템플릿 정의'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: ed66d51e87a25f74e646d0d535ac9e4ee9c8a056
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551138"
---
# <a name="how-to-define-a-groupbox-template"></a>방법: GruopBox 템플릿 정의
에 대 한 템플릿을 만드는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.GroupBox> 제어 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 정의 <xref:System.Windows.Controls.GroupBox> 컨트롤 템플릿을 사용 하 여 한 <xref:System.Windows.Controls.Grid> 레이아웃에 대 한 제어 합니다. 템플릿을 사용 하 여 한 <xref:System.Windows.Controls.BorderGapMaskConverter> 의 테두리를 정의 하는 <xref:System.Windows.Controls.GroupBox> 테두리를 가리지 않습니다 있도록는 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 콘텐츠입니다.  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.GroupBox>  
 [GroupBox 방법 도움말 항목](http://msdn.microsoft.com/library/7692e155-a4c6-428c-b7e0-64b3740daca7)
