---
title: '방법: 이미지 회전, 반사 및 기울이기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: 7f580b4d3016f1ecedc33302fe57caeec5698aeb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523457"
---
# <a name="how-to-rotate-reflect-and-skew-images"></a>방법: 이미지 회전, 반사 및 기울이기
있습니다 수 회전, 반사 및 기울이기 이미지 원본 이미지의 왼쪽 위, 오른쪽 위 및 왼쪽 아래 모퉁이 대 한 대상 지점을 지정 하 여 합니다. 세 개의 대상 지점 평행 사변형에 원본 사각형이 이미지 매핑되는 3x3 유사 변형을 결정 합니다.  
  
## <a name="example"></a>예제  
 예를 들어, 원본 이미지는 왼쪽 위 모퉁이에 있는 사각형 (0, 0)에서 오른쪽 위 모서리 (100, 0) 및 왼쪽 아래 모퉁이에 (0, 50). 이제 이러한 매핑 한다고 가정 3 개를 가리킵니다 대상 점은 다음과 같습니다.  
  
|원래 지점|대상 지점|  
|--------------------|-----------------------|  
|왼쪽 위 (0, 0)|(200, 20)|  
|오른쪽 위 (100, 0)|(110, 100)|  
|왼쪽 아래 (0, 50)|(250, 30)|  
  
 다음은 원본 이미지와 평행 사변형에 매핑되는 이미지입니다. 원본 이미지 왜곡, 반영, 회전, 되었으며 변환 합니다. 통해 실행 되는 줄에 매핑된 원본 이미지의 위쪽 가장자리를 따라 x 축 (200, 20) 및 (110, 100). 통해 실행 되는 줄에 매핑된 원본 이미지의 왼쪽된 가장자리를 따라 y 축 (200, 20) 및 (250, 30).  
  
 ![줄무늬](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")  
  
 다음 그림과 비슷한 변환을 사진 이미지에 적용 합니다.  
  
 ![오르기 변환](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")  
  
 다음 그림과 비슷한 변환을 메타 파일에 적용 합니다.  
  
 ![메타 파일 변환](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")  
  
 다음 예에서는 첫 번째 그림에 표시 된 이미지를 생성 합니다.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다. 대체 해야 `Stripes.bmp` 은 시스템에서 사용할 수 있는 이미지의 경로 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [이미지, 비트맵, 아이콘 및 메타파일 사용](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
