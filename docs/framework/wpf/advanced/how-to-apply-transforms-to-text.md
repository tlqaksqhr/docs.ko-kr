---
title: "방법: 텍스트에 변환 적용 | Microsoft Docs"
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
  - "회전된 텍스트"
  - "배율 조정된 텍스트"
  - "숨겨진 텍스트"
  - "기울어진 텍스트"
  - "텍스트의 변환"
  - "변환된 텍스트"
  - "입력 체계, 회전된 텍스트"
  - "입력 체계, 배율 조정된 텍스트"
  - "입력 체계, 숨겨진 텍스트"
  - "입력 체계, 기울어진 텍스트"
  - "입력 체계, 변환"
  - "입력 체계, 변환된 텍스트"
ms.assetid: 0d61678a-4185-4f2a-85c6-c1d020f96fa0
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# 방법: 텍스트에 변환 적용
변환은 응용 프로그램에서 텍스트의 표시 방식을 변경할 수 있습니다.  다음 예제에서는 다양한 렌더링 변환 형식을 사용하여 <xref:System.Windows.Controls.TextBlock> 컨트롤에서의 텍스트 표시 방식에 영향을 줍니다.  
  
## 예제  
 다음 예제에서는 2차원 x\-y 평면에서 지정한 지점을 중심으로 회전된 텍스트를 보여 줍니다.  
  
 ![RotateTransform을 사용하여 회전된 텍스트](../../../../docs/framework/wpf/advanced/media/transformedtext01.png "TransformedText01")  
90도 회전된 텍스트 예제  
  
 다음 코드 예제에서는 <xref:System.Windows.Media.RotateTransform>을 사용하여 텍스트를 회전합니다.  <xref:System.Windows.Media.RotateTransform.Angle%2A> 값이 90이면 요소가 시계 방향으로 90도 회전됩니다.  
  
 [!code-xml[TextTransformSample#TextTransformSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 다음 예제의 둘째 줄과 셋째 줄에서는 각각 x축 방향으로 150% 확대한 텍스트와 y축 방향으로 150% 확대한 텍스트를 보여 줍니다.  
  
 ![ScaleTransform을 사용하여 배율 조정된 텍스트](../../../../docs/framework/wpf/advanced/media/transformedtext02.png "TransformedText02")  
배율이 조정된 텍스트 예제  
  
 다음 코드 예제에서는 <xref:System.Windows.Media.ScaleTransform>을 사용하여 원래 크기와 다르게 텍스트의 배율을 조정합니다.  
  
 [!code-xml[TextTransformSample#TextTransformSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
>  텍스트의 배율을 조정하는 것은 텍스트의 글꼴 크기를 늘리는 것과 다릅니다.  글꼴 크기는 다양한 크기에서 최상의 해상도를 제공하기 위해 서로 독립적으로 계산되는 반면  배율이 조정된 텍스트는 원래 크기 텍스트의 비율을 유지합니다.  
  
 다음 예제에서는 x축 방향으로 기울인 텍스트를 보여 줍니다.  
  
 ![SkewTransform을 사용하여 기울인 텍스트](../../../../docs/framework/wpf/advanced/media/transformedtext03.png "TransformedText03")  
기울어진 텍스트 예제  
  
 다음 코드 예제에서는 <xref:System.Windows.Media.SkewTransform>을 사용하여 텍스트를 기울입니다.  기울이기는 균일하지 않은 방식으로 좌표 공간을 늘리는 변환입니다.  이 예제에서 두 텍스트 문자열은 x 좌표 방향으로 \-30°와 30° 기울여집니다.  
  
 [!code-xml[TextTransformSample#TextTransformSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 다음 예제에서는 x축과 y축 방향으로 변환되거나 이동된 텍스트를 보여 줍니다.  
  
 ![TranslateTransform을 사용한 텍스트 오프셋](../../../../docs/framework/wpf/advanced/media/transformedtext04.png "TransformedText04")  
변환된 텍스트 예제  
  
 다음 코드 예제에서는 <xref:System.Windows.Media.TranslateTransform>을 사용하여 텍스트를 오프셋합니다.  이 예제에서 기본 텍스트 아래에 있는 약간 오프셋된 텍스트 복사본이 그림자 효과를 만듭니다.  
  
 [!code-xml[TextTransformSample#TextTransformSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
>  <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>는 그림자 효과를 제공하기 위한 다양한 기능 집합을 제공합니다.  자세한 내용은 [그림자가 적용된 텍스트 만들기](../../../../docs/framework/wpf/advanced/how-to-create-text-with-a-shadow.md)를 참조하십시오.  
  
## 참고 항목  
 [텍스트에 애니메이션 적용](../../../../docs/framework/wpf/advanced/how-to-apply-animations-to-text.md)