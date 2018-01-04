---
title: "선 및 채우기 알파 혼합"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- lines [Windows Forms], adding transparency
- examples [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with lines
- alpha blending
- lines [Windows Forms], alpha blending
- fills [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with fills
- shapes [Windows Forms], adding transparency
ms.assetid: 5440f48c-3ac9-44c3-b170-c1c110bdbab8
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a46efeccf9ab343ca0da07fad07138bd72e4e44
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="alpha-blending-lines-and-fills"></a>선 및 채우기 알파 혼합
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], 색이 알파, 빨간색, 녹색 및 파란색에 대 한 8 비트는 32 비트 값입니다. 알파 값 색의 투명도 이면-범위 배경색으로 색 혼합 됩니다. 알파 값 범위는 0에서 255까지, 여기서 0 완전히 투명 한 색을 나타내는 경우 255 완전히 불투명 한 색을 나타냅니다.  
  
 알파 혼합 픽셀 단위의 혼합 원본과 배경 색 데이터입니다. 각 원본 색의 세 가지 구성 (빨강, 녹색, 파랑)는 다음과 같은 식에 따라 배경색의 해당 구성 요소와 혼합 됩니다.  
  
 displayColor sourceColor × 알파 = 255 / backgroundColor × (255-alpha) + 255 /  
  
 예를 들어 소스 색의 빨간색 구성 요소는 150 및 배경 색의 빨강 구성은 100입니다. 알파 값이 200 이면 생성 된 색의 빨강 구성 다음과 같이 계산 됩니다.  
  
 150 × 200 / 255 + 100 × (255 – 200) / 255 = 139  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: 불투명 및 반투명 선 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)  
 알파 혼합 선을 그리는 방법을 보여 줍니다.  
  
 [방법: 불투명 및 반투명 브러시를 사용하여 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 브러시에 알파 혼합 하는 방법을 설명 합니다.  
  
 [방법: 합성 모드를 사용하여 알파 혼합 조절](../../../../docs/framework/winforms/advanced/how-to-use-compositing-mode-to-control-alpha-blending.md)  
 사용 하 여 알파 혼합을 제어 하는 방법을 설명 <xref:System.Drawing.Drawing2D.CompositingMode>합니다.  
  
 [방법: 색 매트릭스를 사용하여 이미지에 알파 값 설정](../../../../docs/framework/winforms/advanced/how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 사용 하는 방법에 설명 된 <xref:System.Drawing.Imaging.ColorMatrix> 알파 혼합을 제어 하는 개체입니다.
