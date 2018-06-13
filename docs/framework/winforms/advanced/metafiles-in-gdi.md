---
title: GDI+의 메타파일
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
ms.openlocfilehash: 73cacb7f701768b42121c31cfbc4f26905961231
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525098"
---
# <a name="metafiles-in-gdi"></a>GDI+의 메타파일
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 제공 된 <xref:System.Drawing.Imaging.Metafile> 클래스를 기록 하 고 메타 파일을 표시할 수 있도록 합니다. 벡터 이미지 라고도 불리는 메타 파일 그리기 명령 및 설정의 시퀀스로 저장 되는 이미지를입니다. 명령 및 설정에 기록 된 <xref:System.Drawing.Imaging.Metafile> 개체를 메모리에 저장 되거나를 파일이 나 스트림에 저장할 수 있습니다.  
  
## <a name="metafile-formats"></a>메타 파일 형식  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 다음 형식으로 저장 된 메타 파일을 표시할 수 있습니다.  
  
-   Windows 메타 파일 WMF)  
  
-   EMF(확장 메타파일)  
  
-   EMF +  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] WMF 형식의 있지만 EMF 및 EMF + 형식에 메타 파일을 기록할 수 있습니다.  
  
 EMF +는 emf 수 있는 확장 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 레코드를 저장할 수 있습니다. EMF + 형식에 두 가지 변형이 있습니다: 및 EMF + 복합 EMF +만 합니다. 메타 파일 EMF +만 포함 될 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 레코드입니다. 이러한 메타 파일은 표시할 수 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 하지만 하지 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]합니다. EMF + 복합 메타 파일 포함 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 및 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 레코드입니다. 각 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 레코드 EMF + 복합에 메타 파일 쌍을 이룹니다 대체 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 레코드입니다. 이러한 메타 파일은 표시할 수 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 또는 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]합니다.  
  
 다음 예제에서는 이전에 파일로 저장 된 메타 파일을 표시 합니다. 메타 파일은 왼쪽 위 모퉁이 표시 됩니다 (100, 100).  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>참고 항목  
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
