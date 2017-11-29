---
title: "그라데이션 브러시를 사용하여 도형 채우기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5a1c4ab7c2ee6f7164b6158dcb4ca4721be12650
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a>그라데이션 브러시를 사용하여 도형 채우기
셰이프를 채우는 효과와 그라데이션 브러시를 사용할 수 있습니다. 예를 들어는 가로 그라데이션을 셰이프를 채우는 모양의 왼쪽된 가장자리에서 맨 오른쪽으로 이동 하면 점진적으로 변경 하는 색으로 사용할 수 있습니다. 검정 왼쪽된 가장자리에 사각형을 가정해 보세요 (0, 0, 0 빨강, 녹색 및 파랑 구성 요소에 의해 표현 됨)는 오른쪽 가장자리 빨강 (255, 0, 0)는 및입니다. 사각형이 256 픽셀 너비 경우 각된 픽셀의 빨간색 구성 요소는 왼쪽에 픽셀의 빨간색 구성 요소 보다 1 큽니다 됩니다. 행에서 가장 왼쪽에 있는 픽셀의 색 구성 요소 (0, 0, 0), 두 번째 픽셀은 (1, 0, 0), 세 번째 픽셀에는 (2, 0, 0)은, 및 기타 등등을 오른쪽에 있는 픽셀의 색 구성 요소 (255, 0, 0)에 도달할 때까지 합니다. 이러한 방식된으로 색 값 색 그라데이션의 구성 합니다.  
  
 가로, 세로 이동 하거나 지정된 된 기울어진된 줄으로 병렬 선형 그라데이션 색을 변경 합니다. 내부 및 경로의 경계에 대 한 이동 하면 경로 그라데이션 색을 변경 합니다. 경로 그라데이션 다양 한 효과 달성 하기 위해 사용자 지정할 수 있습니다.  
  
 다음 그림에서는 선형 그라데이션 브러시 채워진 사각형 및 타원 경로 그라데이션 브러시 채워진 보여 줍니다.  
  
 ![그라데이션](../../../../docs/framework/winforms/advanced/media/gradient2.png "gradient2")  
  
## <a name="in-this-section"></a>단원 내용  
 [방법: 선형 그라데이션 만들기](../../../../docs/framework/winforms/advanced/how-to-create-a-linear-gradient.md)  
 사용 하 여 선형 그라데이션 만드는 방법을 보여 줍니다.는 <xref:System.Drawing.Drawing2D.LinearGradientBrush> 클래스입니다.  
  
 [방법: 경로 그라데이션 만들기](../../../../docs/framework/winforms/advanced/how-to-create-a-path-gradient.md)  
 사용 하는 경로 그라데이션를 만드는 방법에 설명 된 <xref:System.Drawing.Drawing2D.PathGradientBrush> 클래스입니다.  
  
 [방법: 그라데이션에 감마 보정 적용](../../../../docs/framework/winforms/advanced/how-to-apply-gamma-correction-to-a-gradient.md)  
 그라데이션 브러시로 감마 보정을 사용 하는 방법에 설명 합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 이 클래스에 대 한 설명을 포함 하 고 모든 해당 멤버의 링크를 포함 합니다.  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 이 클래스에 대 한 설명을 포함 하 고 모든 해당 멤버의 링크를 포함 합니다.
