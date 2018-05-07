---
title: '방법: 영역을 사용하여 적중 테스트'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 40297fada3d042aee8c317eb787de03662f86cfc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-hit-testing-with-a-region"></a>방법: 영역을 사용하여 적중 테스트
적중 횟수 테스트의 목적은 커서가 아이콘 또는 단추와 같은 특정된 개체 위에 있는지 여부를 결정 하는 것입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 개의 사각형 영역 결합 하 여 더하기 모양의 영역을 만듭니다. 가정 변수 `point` 가장 최근에 클릭 위치를 보유 합니다. 확인 하는 코드 있는지 여부를 `point` 더하기 모양의 지역에 있습니다. 지점이 (적중) 지역에 있으면 빨간색 불투명 브러시는 지역이 채워집니다. 그렇지 않으면 지역 빨간색 반투명 브러시를 채워집니다.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Region>  
 [GDI+의 영역](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)  
 [방법: 영역을 사용하여 클리핑](../../../../docs/framework/winforms/advanced/how-to-use-clipping-with-a-region.md)
