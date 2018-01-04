---
title: "방법: XAML에서 특수 문자 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 79df87d716224cb8681c1688d94fe56077452c1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-special-characters-in-xaml"></a>방법: XAML에서 특수 문자 사용
마크업 파일에 만들어진 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 에 자동으로 저장 되는 [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] u t F-8 파일 형식 이므로 악센트 표시 등의 가장 특수 문자가 인코딩됩니다. 그러나 다르게 처리되는 일반적으로 사용되는 특수 문자 집합이 있습니다. 이 특수 문자에 따라는 [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 인코딩에 대 한 표준입니다.  
  
 다음 표는 이 특수 문자 집합을 인코딩하는 구문을 보여 줍니다.  
  
|문자|구문|설명|  
|---------------|------------|-----------------|  
|<|`<`|보다 작음 기호|  
|>|`>`|보다 큼 기호|  
|&|`&`|앰퍼샌드 기호|  
|"|`"`|큰따옴표 기호|  
  
> [!NOTE]
>  파일을 만들면 태그 텍스트를 사용 하 여 편집기와 같은 경우 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 메모장에서 파일을 저장 해야는 [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] 인코딩된 특수 문자를 보존할 u t F-8 파일 형식입니다.  
  
 다음 예제에서는 태그를 만들 때 텍스트에 특수 문자를 사용하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
