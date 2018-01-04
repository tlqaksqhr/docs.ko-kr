---
title: "방법: GruopBox 템플릿 정의"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1a63a79b298a45b4efd6d1cbd439d208744358ea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-a-groupbox-template"></a>방법: GruopBox 템플릿 정의
에 대 한 템플릿을 만드는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.GroupBox> 제어 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 정의 <xref:System.Windows.Controls.GroupBox> 컨트롤 템플릿을 사용 하 여 한 <xref:System.Windows.Controls.Grid> 레이아웃에 대 한 제어 합니다. 템플릿을 사용 하 여 한 <xref:System.Windows.Controls.BorderGapMaskConverter> 의 테두리를 정의 하는 <xref:System.Windows.Controls.GroupBox> 테두리를 가리지 않습니다 있도록는 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 콘텐츠입니다.  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.GroupBox>  
 [GroupBox 방법 도움말 항목](http://msdn.microsoft.com/en-us/7692e155-a4c6-428c-b7e0-64b3740daca7)
