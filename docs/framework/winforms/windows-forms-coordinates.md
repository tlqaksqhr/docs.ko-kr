---
title: Windows Forms 좌표
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms coordinates
- screen coordinates
- client coordinates
- coordinates [Windows Forms], Windows Forms
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
ms.openlocfilehash: ba6bf8c1a8ae5ab14a9b33ae431e34310046b2a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537878"
---
# <a name="windows-forms-coordinates"></a>Windows Forms 좌표
Windows Form에 대 한 좌표계 장치 좌표를 기반으로 하며 Windows Forms에 그리기 하는 경우 측정값의 기본 단위는 장치 단위 (일반적으로 픽셀)입니다. X-좌표는 오른쪽으로, 위쪽에서 아래쪽 증가 y 좌표가 증가 화면의 점은 x 및 y 좌표 쌍에 의해 설명 합니다. 화면 출처의 위치는 화면 또는 클라이언트 좌표를 지정 하는 여부에 따라 달라 집니다.  
  
## <a name="screen-coordinates"></a>화면 좌표  
 Windows Forms 응용 프로그램 화면 좌표에서 화면에서 창의 위치를 지정합니다. 화면 좌표에 대 한 화면의 왼쪽 위 모서리 원점은 있습니다. 창의 전체 위치에서 설명한 종종는 <xref:System.Drawing.Rectangle> 창의 왼쪽 위 및 오른쪽 아래 모퉁이 정의 하는 두 개의 점의 화면 좌표를 포함 하는 구조입니다.  
  
## <a name="client-coordinates"></a>클라이언트 좌표  
 Windows Forms 응용 프로그램 폼 이나 클라이언트 좌표를 사용 하 여 컨트롤에서 점의 위치를 지정 합니다. 클라이언트 좌표에 대 한 원본 컨트롤이 나 폼의 클라이언트 영역의 왼쪽 위 모퉁이입니다. 클라이언트 좌표 응용 프로그램에서 폼 이나 폼 또는 화면 컨트롤의 위치에 관계 없이 컨트롤을 그리는 동안 일관 된 좌표 값을 사용할 수 있는지 확인 합니다.  
  
 클라이언트 영역의 크기에 대해서도 설명으로 <xref:System.Drawing.Rectangle> 영역에 대 한 클라이언트 좌표를 포함 하는 구조입니다. 모든 경우에는 사각형의 왼쪽 위 좌표는 오른쪽 아래 좌표는 제외 하는 동안 클라이언트 영역에 포함 됩니다. 그래픽 작업에서 클라이언트 영역의 오른쪽 및 아래쪽 가장자리를 포함 하지 않습니다. 예를 들어는 <xref:System.Drawing.Graphics.FillRectangle%2A> 메서드는 지정된 된 사각형의 오른쪽 및 아래쪽 가장자리에 가득 차게 됩니다 하지만 이러한 모서리에 포함 되지 것입니다.  
  
## <a name="mapping-from-one-type-of-coordinate-to-another"></a>다른 좌표 유형 매핑  
 경우에 따라 클라이언트 좌표를 화면 좌표에서 지도 해야 합니다. 이 사용 하 여에 쉽게 매핑할 수 있습니다는 <xref:System.Windows.Forms.Control.PointToClient%2A> 및 <xref:System.Windows.Forms.Control.PointToScreen%2A> 에서 사용할 수 있는 메서드는 <xref:System.Windows.Forms.Control> 클래스입니다. 예를 들어는 <xref:System.Windows.Forms.Control.MousePosition%2A> 속성 <xref:System.Windows.Forms.Control> 화면 좌표에서 보고 하지만 클라이언트 좌표로 변환 하는 것이 좋습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Control.PointToClient%2A>  
 <xref:System.Windows.Forms.Control.PointToScreen%2A>
