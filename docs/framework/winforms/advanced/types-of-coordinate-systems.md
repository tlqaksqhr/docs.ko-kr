---
title: 좌표계 형식
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], page
- unit of measure
- world coordinate system
- page coordinate system
- page transformation
- device coordinate system
- world transformation
- coordinate systems
- transformations [Windows Forms], world
ms.assetid: c61ff50a-eb1d-4e6c-83cd-f7e9764cfa9f
ms.openlocfilehash: ff53942cb90721d5411f99b261f90366d039e151
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="types-of-coordinate-systems"></a>좌표계 형식
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 세 개의 좌표 공간을 사용 하 여: 세계, 페이지 및 장치입니다. 세계 좌표 모델링할 특정 그래픽 영역을 사용 하는 좌표 및 좌표를.NET Framework의 메서드에 전달 합니다. 페이지 좌표 폼 또는 컨트롤과 같은 그리기 화면에서 사용 하는 좌표계를 가리킵니다. 장치 좌표는 화면이 나 용지 같은 항목이 그려지는 물리적 장치에서 사용 하는 좌표입니다. 호출을 수행 하면 `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, 전달 하는 지점은 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드-`(0, 0)` 및 `(160, 80)`-세계 좌표 공간에서 됩니다. 하기 전에 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 화면에 줄을 그릴 수, 좌표 변환의 순서를 통해 전달 합니다. 월드 변형을 호출 하는 하나의 변환 페이지 좌표 세계 좌표를 변환 하 고 다른 변환에 페이지 변환을 통해 장치 좌표로 변환 합니다.  
  
## <a name="transforms-and-coordinate-systems"></a>변환 및 좌표계  
 원점은 왼쪽 위 모서리 아닌 클라이언트 영역의 본문에는 좌표계를 작성 하려면 한다고 가정 합니다. 예를 들어, 예를 들어 클라이언트 영역의 왼쪽된 가장자리에서 100 픽셀 성과 50 픽셀 클라이언트 영역의 위쪽에서 시작 되도록 합니다. 다음은 이러한 좌표 시스템입니다.  
  
 ![좌표계](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art01.gif "AboutGdip05_art01")  
  
 호출을 수행 하면 `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, 다음 그림에 표시 된 줄을 가져옵니다.  
  
 ![좌표계](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art02.gif "AboutGdip05_art02")  
  
 세 가지 좌표 공간에서 행의 끝점 좌표는 다음과 같습니다.  
  
|||  
|-|-|  
|World|(0, 0)를 (160, 80)|  
|페이지|(100, 50)를 (260, 130)|  
|장치|(100, 50)를 (260, 130)|  
  
 페이지 좌표 공간은 원래 클라이언트 영역의 왼쪽 위 모서리에 있는 이 경우 항상 됩니다. 또한는 측정 단위의 픽셀 이기 때문에 장치 좌표와 동일 페이지 좌표 note 합니다. 픽셀 (예를 들어 인치) 이외의 값으로 측정 단위를 설정 하는 경우 장치 좌표 페이지 좌표에서 달라질 수 됩니다.  
  
 세계 좌표 페이지 좌표를 매핑하, 전역 변환에서 유지 되는 <xref:System.Drawing.Graphics.Transform%2A> 의 속성은 <xref:System.Drawing.Graphics> 클래스입니다. 앞의 예제에서 월드 변환을 x 방향의 100 단위 및 y 방향의 50 명의 단위는 합니다. 다음 예제에서는 설정의 월드 변형과 <xref:System.Drawing.Graphics> 개체를 사용 하 여 <xref:System.Drawing.Graphics> 앞의 그림에 표시 된 줄을 그릴 개체:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 페이지 변환은 장치 좌표로 페이지 좌표를 매핑합니다. <xref:System.Drawing.Graphics> 클래스를 제공는 <xref:System.Drawing.Graphics.PageUnit%2A> 및 <xref:System.Drawing.Graphics.PageScale%2A> 페이지 변환을 조작에 대 한 속성입니다. <xref:System.Drawing.Graphics> 클래스에는 두 개의 읽기 전용 속성도 제공 <xref:System.Drawing.Graphics.DpiX%2A> 및 <xref:System.Drawing.Graphics.DpiY%2A>, 가로 및 세로 점선 디스플레이 장치의 인치당를 검사 하는 데 있습니다.  
  
 사용할 수는 <xref:System.Drawing.Graphics.PageUnit%2A> 의 속성은 <xref:System.Drawing.Graphics> 픽셀 이외의 다른 측정 단위를 지정 하는 클래스입니다.  
  
> [!NOTE]
>  설정할 수 없습니다.는 <xref:System.Drawing.Graphics.PageUnit%2A> 속성을 <xref:System.Drawing.GraphicsUnit.World>은 물리적 단위가 고 하면 예외가 발생 합니다.  
  
 다음 예제에서 선을 그립니다 (0, 0)에 (2, 1), (2, 1) 포인터가 있는 2 인치 떨어진 곳을 지점 (0, 0)에서 1 인치 아래로:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
>  펜을 생성할 때 펜 너비를 지정 하지 않으면, 앞의 예제 1 인치 너비에 있는 줄을 그립니다. 두 번째 인수에 펜 너비를 지정할 수는 <xref:System.Drawing.Pen> 생성자:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 디스플레이 장치에는 가로 방향는 96dpi와 세로 방향는 96dpi 라고 가정, 앞의 예제에서 줄의 끝점 좌표는 다음과 세 가지 좌표 공간에서:  
  
|||  
|-|-|  
|World|(0, 0)에 (2, 1)|  
|페이지|(0, 0)에 (2, 1)|  
|장치|(0, 0를 (192, 96)|  
  
 Note 클라이언트 영역의 왼쪽 위 모퉁이에 원점 세계 좌표 공간의 이기 때문에 페이지 좌표는 세계 좌표와 동일 합니다.  
  
 다양 한 효과 달성 하기 위해 월드 및 페이지 변환을 결합할 수 있습니다. 예를 들어 인치 측정 단위로 사용 하 고 클라이언트 영역 및 클라이언트 영역의 위쪽에서 1/2 인치의 왼쪽된 가장자리에서 2 인치로 좌표 시스템의 원점이 됩니다. 다음 예제에서는 설정의 월드 및 페이지 변환을 <xref:System.Drawing.Graphics> 개체를 다음에서 선을 그립니다 (0, 0)에 (2, 1):  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 다음 그림에서는 줄과 좌표 시스템을 보여 줍니다.  
  
 ![좌표계](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art03.gif "AboutGdip05_art03")  
  
 디스플레이 장치에는 가로 방향는 96dpi와 세로 방향는 96dpi 라고 가정, 앞의 예제에서 줄의 끝점 좌표는 다음과 세 가지 좌표 공간에서:  
  
|||  
|-|-|  
|World|(0, 0)에 (2, 1)|  
|페이지|(2, 0.5)를 (4, 1.5)|  
|장치|(192, 48)에 (384, 144)|  
  
## <a name="see-also"></a>참고 항목  
 [좌표계 및 변형](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [매트릭스에 의한 변형 표시](../../../../docs/framework/winforms/advanced/matrix-representation-of-transformations.md)
