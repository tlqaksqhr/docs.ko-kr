---
title: "ColorConvertedBitmap 태그 확장 | Microsoft Docs"
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
  - "ColorConvertedBitmap 태그 확장"
  - "XAML, ColorConvertedBitmap 태그 확장"
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# ColorConvertedBitmap 태그 확장
포함된 프로필이 없는 비트맵 소스를 지정할 수 있습니다.  비트맵은 이미지 소스 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]이므로 색 컨텍스트\/프로필은 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]로 지정됩니다.  
  
## XAML 특성 사용  
  
```  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" .../>  
```  
  
## XAML 값  
  
|||  
|-|-|  
|`imageSource`|프로필이 없는 비트맵의 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]입니다.|  
|`sourceIIC`|소스 프로필 구성의 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]입니다.|  
|`destinationIIC`|대상 프로필 구성의 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]입니다.|  
  
## 설명  
 이 태그 확장은 <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>와 같은 관련된 이미지 소스 속성 값 집합을 채우기 위한 것입니다.  
  
 특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다.  `ColorConvertedBitmap`\(또는 `ColorConvertedBitmapExtension`\)은 속성 요소 구문에서 사용할 수 없는데 이 값은 확장 식별자 다음에 나오는 문자열인 초기 생성자에서만 값으로 설정할 수 있기 때문입니다.  
  
 `ColorConvertedBitmap`은 태그 확장입니다.  태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 모든 태그는 태그의 특성 구문에 { 및 } 문자를 사용하며 여기서 특성 구문은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에 태그 확장이 특성을 처리해야 한다는 것을 인식하는 규칙입니다.  자세한 내용은 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>   
 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [이미징 개요](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)