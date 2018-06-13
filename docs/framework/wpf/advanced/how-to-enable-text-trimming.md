---
title: '방법: 텍스트 잘라내기 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], trimming
- documents [WPF], trimmng text
- trimmng text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
ms.openlocfilehash: 97bc88b298500892fcc7d26e61f8052a05d9e593
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543542"
---
# <a name="how-to-enable-text-trimming"></a>방법: 텍스트 잘라내기 사용
사용 및에서 사용할 수 있는 값의 효과 보여 주는이 예제는 <xref:System.Windows.TextTrimming> 열거형입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 정의 <xref:System.Windows.Controls.TextBlock> 인 요소는 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> 특성이 설정 합니다.  
  
 [!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]  
  
## <a name="example"></a>예제  
 해당 설정 <xref:System.Windows.TextTrimming> 코드에서 속성은 아래에 나와 있습니다.  
  
 [!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
 [!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]  
  
 잘라내기의 텍스트에 대 한 현재 세 가지가: **CharacterEllipsis**, **WordEllipsis**, 및 **None**합니다.  
  
 때 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> 로 설정 된 **CharacterEllipsis**, 텍스트 자르고 줄임표가 가장자리에 가장 가까운 문자에서 사용 합니다.  이 설정은 잘리는 경계에 좀 더 가깝게 맞추어 텍스트를 잘라내기 때문에 단어가 부분적으로 잘릴 수 있습니다.  다음 그림에서이 설정의 효과 보여 줍니다.는 <xref:System.Windows.Controls.TextBlock> 위에 정의 된 것과 비슷한 합니다.  
  
 ![예: TextTrimming.CharacterEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-character.png "TextTrimming_Character")  
  
 때 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> 로 설정 된 **WordEllipsis**, 텍스트가 잘려 하 고 가장 가까운 가장자리에서 첫 번째 전체 단어의 끝에 줄임표가 사용 합니다.  이 설정은 부분적으로 트리밍된 단어에 표시 되지 것입니다 이지만로 가장자리에서 근접 하 게 텍스트 잘라내기 하지 때문는 **CharacterEllipsis** 설정 합니다.  다음 그림에서이 설정의 효과 보여 줍니다.는 <xref:System.Windows.Controls.TextBlock> 위에 정의 된 합니다.  
  
 ![예: TextTrimming.WordEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-word.png "TextTrimming_Word")  
  
 때 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> 로 설정 된 **None**, 텍스트 잘리지 수행 됩니다.  이 경우 텍스트가 부모 텍스트 컨테이너의 경계로 잘릴 뿐입니다.  다음 그림에서이 설정의 효과 보여 줍니다.는 <xref:System.Windows.Controls.TextBlock> 위에 정의 된 것과 비슷한 합니다.  
  
 ![예제: TextTrimming.None](../../../../docs/framework/wpf/advanced/media/texttrimming-none.png "TextTrimming_None")
