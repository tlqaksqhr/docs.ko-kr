---
title: 중첩된 Graphics 컨테이너 사용
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], nested containers
- graphics [Windows Forms], clipping
- graphics [Windows Forms], transformations in nested objects
ms.assetid: a0d9f178-43a4-4323-bb5a-d3e3f77ae6c1
ms.openlocfilehash: ba6bba84100a0ddcc87894710a6d3099ab0ccff5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529063"
---
# <a name="using-nested-graphics-containers"></a>중첩된 Graphics 컨테이너 사용
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 일시적으로 바꾸거나의 상태 부분을 확장 하는 데 사용할 수 있는 컨테이너를 제공는 <xref:System.Drawing.Graphics> 개체입니다. 호출 하 여 컨테이너를 만들는 <xref:System.Drawing.Graphics.BeginContainer%2A> 의 메서드는 <xref:System.Drawing.Graphics> 개체입니다. 호출할 수 있습니다 <xref:System.Drawing.Graphics.BeginContainer%2A> 반복 하 여 중첩 된 컨테이너를 형성 합니다. 호출할 때마다 <xref:System.Drawing.Graphics.BeginContainer%2A> 을 호출 하 여 쌍이 되어야 합니다 <xref:System.Drawing.Graphics.EndContainer%2A>합니다.  
  
## <a name="transformations-in-nested-containers"></a>중첩된 컨테이너에서 변환  
 다음 예제에서는 한 <xref:System.Drawing.Graphics> 안에 컨테이너 및 개체 <xref:System.Drawing.Graphics> 개체입니다. 월드 변형과 <xref:System.Drawing.Graphics> 개체는 x 방향으로 100 변환 단위와 y 방향의 80 단위입니다. 컨테이너의 월드 변형과 30도 회전입니다. 코드에서는 호출 `DrawRectangle(pen, -60, -30, 120, 60)` 두 번입니다. 첫 번째 호출 <xref:System.Drawing.Graphics.DrawRectangle%2A> ; 컨테이너 내부 즉, 전에 수행 됩니다에 대 한 호출 <xref:System.Drawing.Graphics.BeginContainer%2A> 및 <xref:System.Drawing.Graphics.EndContainer%2A>합니다. 두 번째 호출으로 <xref:System.Drawing.Graphics.DrawRectangle%2A> 에 대 한 호출 후 <xref:System.Drawing.Graphics.EndContainer%2A>합니다.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.MiscLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#61)]  
  
 위의 코드에서 컨테이너 내에서 그린 사각형은 먼저 변형 (회전) 컨테이너의 월드 변형과 순위별로 정리한 다음의 월드 변형과 <xref:System.Drawing.Graphics> 개체 (번역). 컨테이너 외부 그린 사각형의 월드 변형과 의해서만 변환 되는 <xref:System.Drawing.Graphics> 개체 (번역). 다음 그림에서는 두 개의 사각형을 보여 줍니다.  
  
 ![컨테이너를 중첩](../../../../docs/framework/winforms/advanced/media/csnestedcontainers1.png "csnestedcontainers1")  
  
## <a name="clipping-in-nested-containers"></a>중첩 된 컨테이너에서 클리핑  
 다음 예제에서는 어떻게 중첩 된 컨테이너 클리핑 영역을 처리 합니다. 코드는 만듭니다는 <xref:System.Drawing.Graphics> 안에 컨테이너 및 개체 <xref:System.Drawing.Graphics> 개체입니다. 클립 영역에서 <xref:System.Drawing.Graphics> 개체 사각형 이며 컨테이너의 클립 영역 타원입니다. 코드를 두 번 호출에서는 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드. 첫 번째 호출 <xref:System.Drawing.Graphics.DrawLine%2A> 컨테이너 및 두 번째 호출으로 내 <xref:System.Drawing.Graphics.DrawLine%2A> 컨테이너를 벗어납니다 (호출 후 <xref:System.Drawing.Graphics.EndContainer%2A>). 첫 번째 줄은 두 개의 클리핑 영역의 교차에 의해 잘립니다. 두 번째 줄의 사각형 오려낸 영역에 의해서만 클리핑됩니다는 <xref:System.Drawing.Graphics> 개체입니다.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#62](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#62)]
 [!code-vb[System.Drawing.MiscLegacyTopics#62](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#62)]  
  
 다음 그림은 두 잘린된 줄을 보여 줍니다.  
  
 ![컨테이너를 중첩](../../../../docs/framework/winforms/advanced/media/nestedcontainers2.png "nestedcontainers2")  
  
 두 개의 이전 예와 같이, 변환 및 클리핑 영역에 중첩 된 컨테이너에 누적 됩니다. 컨테이너의 전역 변형을 설정 하는 경우 및 <xref:System.Drawing.Graphics> 개체를 두 가지 변환은 모두 컨테이너 내에서 선택 항목에 적용 됩니다. 먼저 적용된 및 변형 하는 컨테이너의 변형 됩니다는 <xref:System.Drawing.Graphics> 개체가 두 번째 적용 됩니다. 컨테이너의 클립 영역을 설정 하는 경우 및 <xref:System.Drawing.Graphics> 개체를 항목 컨테이너 내에서 가져온 두 개의 클리핑 영역의 교차에 의해 잘립니다.  
  
## <a name="quality-settings-in-nested-containers"></a>중첩 된 컨테이너에서 품질 설정  
 품질 설정 (<xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.TextRenderingHint%2A>, 등)에 중첩 된 컨테이너는 누적 하지 않습니다; 대신, 컨테이너의 품질 설정의 품질 설정의 임시로 대체는 <xref:System.Drawing.Graphics> 개체입니다. 새 컨테이너를 만들 때 해당 컨테이너에 대 한 품질 설정은 기본값으로 설정 됩니다. 예를 들어 있다고 가정는 <xref:System.Drawing.Graphics> 개체의 다듬기 모드 <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>합니다. 컨테이너를 만들면 컨테이너 안의 다듬기 모드 다듬기 모드 기본값입니다. 컨테이너의 다듬기 모드를 설정 하려면 무료 이며 컨테이너 내에서 가져온 모든 항목에 설정한 모드에 따라 그려집니다. 호출한 후 그리는 항목 <xref:System.Drawing.Graphics.EndContainer%2A> 다듬기 모드에 따라 그려집니다 (<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>)에 대 한 호출 전의 상태로 복원 하는 <xref:System.Drawing.Graphics.BeginContainer%2A>합니다.  
  
## <a name="several-layers-of-nested-containers"></a>중첩 된 컨테이너의 여러 계층  
 하나의 컨테이너에 제한 되지 않습니다는 <xref:System.Drawing.Graphics> 개체입니다. 시퀀스 컨테이너를 만들 수 있습니다 하 고 앞에 중첩 된 각 전역 변환, 클리핑 영역 및 중첩된 된 컨테이너의 각 품질 설정을 지정할 수 있습니다. 가장 안쪽 컨테이너 내에서 그리기 메서드를 호출 하는 경우 변환은 안쪽 컨테이너 시작 및 끝 가장 바깥쪽 컨테이너와 순서로 적용 됩니다. 가장 안쪽 컨테이너 내에서 가져온 항목의 모든 클리핑 영역 교차에 의해 잘립니다.  
  
 다음 예제에서는 한 <xref:System.Drawing.Graphics> 개체 하 고 텍스트 렌더링 힌트 설정 <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>합니다. 코드 내에서 다른 중첩 된 두 개의 컨테이너를 만듭니다. 로 설정 되어 외부 컨테이너의 텍스트 렌더링 힌트 <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>, 내부 컨테이너의 텍스트 렌더링 힌트로 설정 되어 <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>합니다. 코드는 세 개의 문자열을 그립니다: 내부 컨테이너는 외부 컨테이너에서 하나, 하나는에서는 <xref:System.Drawing.Graphics> 개체 자체입니다.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#63](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#63)]
 [!code-vb[System.Drawing.MiscLegacyTopics#63](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#63)]  
  
 다음은 세 개의 문자열입니다. 그리는 및 내부 컨테이너에서 문자열은 <xref:System.Drawing.Graphics> 개체 앤티 앨리어싱 여 다듬어집니다. 외부 컨테이너에서 가져온 문자열 앤티 앨리어싱 여 그라데이션이 없습니다 때문에 <xref:System.Drawing.Graphics.TextRenderingHint%2A> 속성이 <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>합니다.  
  
 ![컨테이너를 중첩](../../../../docs/framework/winforms/advanced/media/nestedcontainers3.png "nestedcontainers3")  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Graphics>  
 [Graphics 개체의 상태 관리](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)
