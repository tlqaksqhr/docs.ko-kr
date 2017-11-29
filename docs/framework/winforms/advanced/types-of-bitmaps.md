---
title: "비트맵의 유형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- jpeg files
- TIFF files
- gif files
- Graphics Interchange Format
- Joint Photographic Experts Group
- .jpeg files
- .gif files
- graphics [Windows Forms], file formats
- images [Windows Forms], file formats
- Portable Network Graphics
- .bmp files
- EXIF file format
- PNG files
- pictures [Windows Forms], file formats
- Tag Image File Format
- bitmaps [Windows Forms], file format
- Exchangeable Image File
ms.assetid: 6be085a2-2c13-47c8-b80a-c18b32777d8d
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b33e710e7f57e1a84372dc556d904e32584a75ea
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="types-of-bitmaps"></a>비트맵의 유형
비트맵은 픽셀의 사각형 배열에서 각 픽셀의 색을 지정 하는 비트의 배열입니다. 각 픽셀에 사용 되는 비트 수는 해당 픽셀에 지정할 수 있는 색 수를 결정 합니다. 예를 들어 각 픽셀을 4 비트로 표시할 다음 지정된 된 픽셀 수 할당할 수 16 다른 색상 중 하나로 (2 ^4 = 16). 다음 표에서 비트의 지정 된 수로 표현 되는 픽셀을 지정할 수 있는 색 수가 몇 가지 예를 보여 줍니다.  
  
|픽셀당 비트 수|픽셀을 지정할 수 있습니다. 있는 색 수|  
|--------------------|------------------------------------------------------|  
|1|2^1 = 2|  
|2|2^2 = 4|  
|4|2^4 = 16|  
|9|2^8 = 256|  
|16|2^16 = 65,536|  
|24|2^24 = 16,777,216|  
  
 일반적으로 비트맵을 저장 하는 디스크 파일 배열에 있는 행의 수, 각 행의 픽셀 수 및 픽셀당 비트 수와 같은 정보를 저장 하는 하나 이상의 정보 블록을 포함 합니다. 이러한 파일 (색상표) 색상표를 포함할 수도 있습니다. 색상표를 특정 색 비트맵에 대응 합니다. 다음 그림에서는 비트맵 및 색 테이블에 맞게 함께 확대 이미지를 보여 줍니다. 있으므로 2는 각 픽셀 4 비트 숫자를 나타내는 ^4 = 16 색상표에서 색을 지정 합니다. 테이블의 각 색은 24 비트 번호로 표시: 8 비트 빨강, 녹색에 대 한 8 비트 및 파란색에 대 한 8 비트입니다. 숫자는 16 진수 (밑수 16) 형태로 표시: A = 10, B = 11, C = 12, D = 13, E = 14, F = 15입니다.  
  
 ![비트맵 샘플](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art01.gif "AboutGdip03_Art01")  
  
 3, 열 5 이미지의 행에 있는 픽셀을 살펴봅니다. 비트맵에서 해당 번호는 1입니다. 색상표에 따르면 1은 나타내기 빨간색 픽셀은 빨간색입니다. 비트맵의 맨 위 행에 있는 모든 항목은 3입니다. 색상표 때문 모든 픽셀 이미지의 맨 위 행은 파랑 3은 파랑을 알려줍니다.  
  
> [!NOTE]
>  일부 비트맵 상향식 형식으로 저장 됩니다. 비트맵의 첫 번째 행의 번호는 이미지의 아래쪽 행에 있는 픽셀에 해당합니다.  
  
 색 테이블에 인덱스를 저장 하는 비트맵 색상표에 인덱싱된 비트맵을 라고 합니다. 어떤 비트맵은 색 테이블에 대 한 필요가 없습니다. 예를 들어 비트맵 픽셀 당 24 비트를 사용 하는 경우 해당 비트맵 저장할 수 인덱스 대신 자체 색 색상표에. 다음 그림은 색상표를 사용 하 여 (24 비트 / 픽셀) 색을 직접 저장 하는 비트맵입니다. 그림에는 해당 이미지의 확대해 보여 줍니다. 비트맵 형식으로 FFFFFF은 흰색을 나타냅니다, 그리고 f f 0000 나타내는 빨강, 00FF00 녹색, 나타내며 0000ff>microsoft 파란색입니다.  
  
 ![비트맵 샘플](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art02.gif "AboutGdip03_Art02")  
  
## <a name="graphics-file-formats"></a>그래픽 파일 형식  
 디스크 파일의 비트맵을 저장 하기 위한 다양 한 표준 형식 있습니다. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]다음 단락에서 설명한 형식 파일 그래픽 지원 합니다.  
  
### <a name="bmp"></a>BMP  
 BMP는 장치 및 응용 프로그램 독립적인 이미지를 저장할 Windows에서 사용 되는 표준 형식입니다. 주어진된 BMP 파일에 대 한 (1, 4, 8, 15, 24, 32 또는 64) 픽셀당 비트 수 파일 헤더에 지정 됩니다. 24 비트 / 픽셀을 사용 하 여 BMP 파일은 공통적입니다. BMP 파일은 일반적으로 압축 되지 않습니다 및 따라서 적합 하지 않습니다 전송에 대 한 인터넷을 통해.  
  
### <a name="graphics-interchange-format-gif"></a>GIF(Graphics Interchange Format)  
 GIF은 웹 페이지에 표시 되는 이미지에 대 한 일반적인 형식입니다. 선 그리기, 단색 블록을 사용 하 여 사진 및 색상 사이의 날카로운 경계와 사진을 대해 제대로 Gif 작동 합니다. Gif는 압축 되지만 압축 프로세스; 정보가 손실 압축 푼된 이미지 원래와 정확히 같습니다. 수 있도록 이미지 표시 하는 모든 웹 페이지의 배경색 gif 이미지에서 색을 투명으로 지정 될 수 있습니다. GIF 이미지의 시퀀스는 애니메이션된 GIF를 형성 하는 단일 파일에 저장할 수 있습니다. Gif 저장 픽셀 당 최대 8 비트 256 색이 제한 됩니다.  
  
### <a name="joint-photographic-experts-group-jpeg"></a>Joint Photographic Experts Group (JPEG)  
 JPEG 스캔 한 사진과 같은 자연 스런 장면에 대해 제대로 작동 하는 압축 체계입니다. 압축 프로세스에서 일부 정보가 손실 하지만 손실 육안으로 감지할 수 없는 경우가 많습니다. Jpeg은 16 백만 개 이상의 색을 표시할 수 있도록 24 비트 / 픽셀을 저장 합니다. 투명도 또는 애니메이션 Jpeg 지원 하지 않습니다.  
  
 JPEG 이미지의 압축 수준 구성 가능 하지만 더 많은 정보가 손실을 할 더 높은 압축 수준을 (더 작은 파일). 20:1 압축 비율은 종종 육안 원래 구분 하기 어려운 발견 하는 이미지를 생성 합니다. 다음 그림은 BMP 이미지와 해당 BMP 이미지에서 압축 된 JPEG 이미지를 두 개를 보여 줍니다. 첫 번째 JPEG 4:1 압축 비율은 있고 두 번째 JPEG 8:1 압축 비율은 합니다.  
  
 ![파일 형식 샘플](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art03.gif "AboutGdip03_Art03")  
  
 JPEG 압축 선 그리기 단색 블록에서 잘 작동 하지 않으며 경계 날카로운 합니다. 다음 그림에서는 두 개의 Jpeg, GIF 함께 BMP 보여 줍니다. Jpeg, GIF BMP에서 압축 되었습니다. 더 작은 JPEG에 대 한 및 8:3 보다 큰 JPEG에 대 한의 압축률은 4:1 GIF, 4:1입니다. Note GIF에 따라, 날카로운 경계를 유지 하지만 jpeg 형식을 경계 흐리게 표시 하는 경향이 있습니다.  
  
 ![파일 형식이](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art03a.gif "AboutGdip03_Art03A")  
  
 JPEG 압축 체계에는 파일 형식입니다. JPEG 파일 교환 형식 (JFIF)는 일반적으로 저장 하 고 JPEG 체계에 따라 압축 된 이미지를 전송에 사용 되는 파일 형식입니다. 웹 브라우저에서 표시 된 JFIF 파일.jpg 확장 프로그램을 사용 합니다.  
  
### <a name="exchangeable-image-file-exif"></a>교환 이미지 파일 (EXIF)  
 EXIF는 디지털 카메라에서 찍은 사진에 사용 되는 파일 형식입니다. EXIF 파일 JPEG 사양에 따라 압축 된 이미지를 포함 합니다. EXIF 파일에 대 한 정보도 사진을 (만든 날짜, 속도, 노출 시간 등에 셔터) 및 (제조업체, 모델 및 등) 카메라에 대 한 정보입니다.  
  
### <a name="portable-network-graphics-png"></a>PNG(이동식 네트워크 그래픽)  
 PNG 형식 다양 한 이점을 GIF 형식의 유지 하지만 또한 GIF를 능가 하는 기능을 제공 합니다. GIF 파일 처럼 정보의 손실 없이 PNG 파일 압축 됩니다. PNG 파일에 지정 된 8, 24 또는 48 비트 / 픽셀 및 회색조를 1, 2, 4, 8 또는 16 비트 / 픽셀 색을 저장할 수 있습니다. 반면, 1, 2, 4 또는 8 비트 / 픽셀 GIF 파일 사용할 수 있습니다. PNG 파일을 해당 픽셀의 색이 배경색과 혼합 됩니다 배경색 정도 지정 하는 각 픽셀에 대 한 알파 값을 저장할 수도 있습니다.  
  
 점진적으로 이미지를 표시 하는 능력에 GIF 개선 PNG (즉, 더 선명 이미지의 것으로 표시 하려면 도착 하면 네트워크 연결을 통해). 다양 한 디스플레이 장치에 이미지를 정확 하 게 표시할 수 있도록 PNG 파일 감마 보정 및 색 보정 정보를 포함할 수 있습니다.  
  
### <a name="tag-image-file-format-tiff"></a>Tag Image File Format TIFF)  
 TIFF는 다양 한 플랫폼 및 이미지 처리 응용 프로그램에서 사용할 수 있는 유연 하 고 확장 가능한 형식입니다. TIFF 파일 임의 개수의 픽셀 당 비트를 사용 하 여 이미지 저장 하 고 다양 한 압축 알고리즘을 사용할 수 있습니다. 몇 가지 이미지가 단일 다중 페이지 TIFF 파일에 저장할 수 있습니다. (스캐너 만들기, 호스트 컴퓨터, 압축, 방향, 픽셀에, 및 기타 등등 당 샘플 유형의) 이미지와 관련 정보를 파일에 저장 하 고 태그를 사용 하 여 정렬할 수 있습니다. TIFF 형식의 승인 하 고 새 태그의 추가가 필요에 따라 확장할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Image?displayProperty=nameWithType>  
 <xref:System.Drawing.Bitmap?displayProperty=nameWithType>  
 <xref:System.Drawing.Imaging.PixelFormat?displayProperty=nameWithType>  
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [이미지, 비트맵, 아이콘 및 메타파일 사용](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
