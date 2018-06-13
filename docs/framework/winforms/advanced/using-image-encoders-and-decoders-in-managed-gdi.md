---
title: 관리 GDI+에서 이미지 인코더 및 디코더 사용
ms.date: 03/30/2017
helpviewer_keywords:
- image encoders [Windows Forms], using
- image decoders [Windows Forms], using
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
ms.openlocfilehash: b2e51587209cb4df41ea1fd18ce5c2088ee07a2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524503"
---
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a>관리 GDI+에서 이미지 인코더 및 디코더 사용
<xref:System.Drawing> 네임 스페이스는 제공 된 <xref:System.Drawing.Image> 및 <xref:System.Drawing.Bitmap> 저장 및 이미지 조작을 위한 클래스입니다. 이미지 인코더를 사용 하 여 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], 디스크에 메모리에서 이미지를 작성할 수 있습니다. 이미지 디코더를 사용 하 여 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], 메모리에 디스크에서 이미지를 로드할 수 있습니다. 데이터를 변환 하는 인코더는 <xref:System.Drawing.Image> 또는 <xref:System.Drawing.Bitmap> 개체를 지정 된 디스크 파일 형식입니다. 데이터 원본에 디스크 파일에 데이터를 해석 하는 디코더는 <xref:System.Drawing.Image> 및 <xref:System.Drawing.Bitmap> 개체입니다.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 기본 제공 인코더 및 디코더는 다음 파일 형식을 지 원하는 있습니다.  
  
-   BMP  
  
-   GIF  
  
-   JPEG  
  
-   PNG  
  
-   TIFF  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 다음 파일 형식을 지 원하는 기본 제공 디코더가 있습니다.  
  
-   WMF  
  
-   EMF  
  
-   아이콘  
  
 다음 항목에서는 인코더 및 디코더 더 자세하게에서 설명합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: 설치된 인코더 나열](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 컴퓨터에서 사용할 수 있는 인코더 나열 하는 방법을 설명 합니다.  
  
 [방법: 설치된 디코더 나열](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)  
 컴퓨터에서 사용할 수 있는 디코더 나열 하는 방법을 설명 합니다.  
  
 [방법: 인코더에서 지원하는 매개 변수 확인](../../../../docs/framework/winforms/advanced/how-to-determine-the-parameters-supported-by-an-encoder.md)  
 나열 하는 방법에 설명 된 <xref:System.Drawing.Imaging.EncoderParameters> 인코더에서 지원 합니다.  
  
 [방법: BMP 이미지를 PNG 이미지로 변환](../../../../docs/framework/winforms/advanced/how-to-convert-a-bmp-image-to-a-png-image.md)  
 다른 이미지 형식으로 이미지를 저장 하는 방법에 설명 합니다.  
  
 [방법: JPEG 압축 수준 설정](../../../../docs/framework/winforms/advanced/how-to-set-jpeg-compression-level.md)  
 이미지의 품질 수준을 변경 하는 방법에 설명 합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a>관련 단원  
 [GDI + 관리 코드 정보](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
  
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
