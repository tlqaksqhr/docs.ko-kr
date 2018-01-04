---
title: "방법: 이미지 자르기 및 배율 조정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], cropping
- images [Windows Forms], scaling
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: de905cf70013098a4282e3f4af092ccbea16ccfd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-crop-and-scale-images"></a>방법: 이미지 자르기 및 배율 조정
<xref:System.Drawing.Graphics> 클래스에는 일부의 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드 중 일부는 원본 및 대상 사각형 하는 매개 변수가 이미지 자르기 및 배율에 사용할 수 있습니다.  
  
## <a name="example"></a>예  
 다음 구성 예제는 <xref:System.Drawing.Image> 있는 Apple.gif 디스크 파일에서 개체입니다. 코드는 원래 크기로 전체 apple 이미지를 그립니다. 호출 된 <xref:System.Drawing.Graphics.DrawImage%2A> 의 메서드는 <xref:System.Drawing.Graphics> 원래 apple 이미지 보다 큰 대상 사각형에 apple 이미지의 일부를 그릴 개체입니다.  
  
 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드 다섯 번째 및 여섯 번째 인수는 세 번째, 네 번째, 지정 된 원본 사각형을 확인 하 여 그리는 데 apple의 어떤 부분을 결정 합니다. 이 경우 apple 너비의 75% 및 높이의 75%로 잘립니다.  
  
 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드를 자른된 apple를 그릴 위치와 대상 사각형을 살펴보면 자른된 apple 있도록 최대 크기를 결정은 두 번째 인수로 지정 합니다. 이 경우 대상 사각형에는 더 넓은 30%, 30% 보다 원래 이미지 크기입니다.  
  
 다음 그림에서 원래 apple 및 확장 된 잘라 나타냅니다.  
  
 ![자르기 및 배율 조정](../../../../docs/framework/winforms/advanced/media/cscropscale1.png "csCropScale1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다. 대체 해야 `Apple.gif` 있는 이미지 파일 이름 및 시스템에서 사용할 수 있는 경로입니다.  
  
## <a name="see-also"></a>참고 항목  
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [이미지, 비트맵, 아이콘 및 메타파일 사용](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
