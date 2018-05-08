---
title: 세 가지 범주의 그래픽 서비스
ms.date: 03/30/2017
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2-D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
ms.openlocfilehash: 5621a2c0bba2e922e62006feba9ca0381181c780
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="three-categories-of-graphics-services"></a>세 가지 범주의 그래픽 서비스
Windows Forms의 그래픽 제공 되는 다음 세 가지 광범위 한 범주에 속합니다.  
  
-   2 차원 (2-d) 벡터 그래픽  
  
-   이미징  
  
-   입력 체계  
  
## <a name="2-d-vector-graphics"></a>2 차원 벡터 그래픽  
 2 차원 벡터 그래픽은 기본 형식입니다. 선, 곡선 및 도형; 예: 좌표 시스템의 점 집합으로 지정 합니다. 예를 들어 직선은 두 끝점으로 지정 및 사각형의 왼쪽 위 모퉁이 숫자 너비 및 높이의 쌍의 위치를 제공 하는 지점으로 지정 됩니다. 단순 경로 직선으로 연결 된 점의 배열에 의해 지정 됩니다. 베 지 어 스플라인을 네 개의 제어 점으로 지정 하는 정교한 곡선입니다.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 클래스 및 기본 형식 자체에 대 한 정보를 저장 하는 구조체, 기본 형식이 그리는 방법,에 대 한 정보를 저장 하는 클래스 및 실제로 그리기를 수행 하는 클래스를 제공 합니다. 예를 들어는 <xref:System.Drawing.Rectangle> 구조; 사각형의 크기와 위치에 저장 되는 <xref:System.Drawing.Pen> 선 색, 줄 너비 및 선 스타일에 대 한 정보를 저장 하는 클래스 및 <xref:System.Drawing.Graphics> 클래스에 선, 사각형, 경로, 그리기 위한 메서드 및 다른 그림입니다. 또한 여러 <xref:System.Drawing.Brush> 방법에 대 한 정보를 저장 하는 클래스 수치 닫히고 경로 색 또는 패턴으로 채워집니다.  
  
 벡터 이미지 그래픽 명령 시퀀스를 메타 파일에 기록할 수 있습니다. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 제공 된 <xref:System.Drawing.Imaging.Metafile> 기록, 표시 및 메타 파일 저장에 대 한 클래스입니다. 와 <xref:System.Drawing.Imaging.MetafileHeader> 및 <xref:System.Drawing.Imaging.MetaHeader> 클래스, 메타 파일 헤더에 저장 된 데이터를 검사할 수 있습니다.  
  
## <a name="imaging"></a>이미징  
 특정 종류의 그림 힘들거나 기술로 벡터 그래픽의 표시를 합니다. 예를 들어 도구 모음 단추에 사진 및 사진 아이콘으로 표시 되는 선 및 곡선의 컬렉션으로 지정 하기 어렵습니다. 꽉된 야구 경기장 고해상도 디지털 사진 벡터 기술로 생성을 훨씬 더 어렵습니다. 이 유형의 이미지는 화면에 각 점의 색을 나타내는 숫자의 배열 하는 비트맵으로 저장 됩니다. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 제공 된 <xref:System.Drawing.Bitmap> 표시, 조작 및 비트맵 저장에 대 한 클래스입니다.  
  
## <a name="typography"></a>입력 체계  
 입력 체계는 다양 한 글꼴, 크기 및 스타일의에서 텍스트 표시 됩니다. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 이러한 복잡 한 작업에 대 한 광범위 한 지원을 제공합니다. 새로운 기능 중 하나 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 가 텍스트를 제공 하는 하위 픽셀 앤티 앨리어싱 렌더링 LCD 화면에서 부드러운 모양으로 표시 합니다.  
  
 또한 Windows Forms에는 텍스트를 그릴 옵션이 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 기능에 해당 <xref:System.Windows.Forms.TextRenderer> 클래스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [그래픽 개요](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)  
 [GDI + 관리 코드 정보](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
 [관리되는 그래픽 클래스 사용](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)
