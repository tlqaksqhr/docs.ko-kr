---
title: "방법: XAML에서 특수 문자 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "문자, 특수"
  - "특수 문자"
  - "입력 체계, 특수 문자"
  - "유니코드 UTF-8 파일 형식"
  - "UTF-8 파일 형식"
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# 방법: XAML에서 특수 문자 사용
[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]에서 작성한 태그 파일은 자동으로 [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF\-8 파일 형식으로 저장됩니다. 따라서 악센트 기호 등의 대부분의 특수 문자가 올바르게 인코딩됩니다.  하지만 이와는 다르게 처리되는 많이 사용되는 특수 문자 집합이 있습니다.  이러한 특수 문자는 [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 표준에 따라 인코딩됩니다.  
  
 다음 표에서는 이 특수 문자 집합을 인코딩하기 위한 구문을 보여 줍니다.  
  
|문자|구문|설명|  
|--------|--------|--------|  
|\<|`<`|보다 작음 기호|  
|\>|`>`|보다 큼 기호|  
|&|`&`|앰퍼샌드 기호|  
|이때|`"`|큰따옴표 기호|  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 메모장과 같은 텍스트 편집기를 사용하여 작성한 태그 파일은 [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF\-8 파일 형식으로 저장해야 인코딩된 특수 문자를 보존할 수 있습니다.  
  
 다음 예제에서는 태그를 작성할 때 텍스트에 특수 문자를 사용하는 방법을 보여 줍니다.  
  
## 예제  
 [!code-xml[SpecialCharsSnippets#SpecialCharsSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]