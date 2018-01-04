---
title: "방법: 입력 마스크 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: net.ComponentModel.MaskPropertyEditor
helpviewer_keywords: MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 68bfe46462a374899a0782903804edea0e93f161
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-input-mask"></a>방법: 입력 마스크 설정
마스킹된 텍스트 상자 컨트롤은 있는 향상 된 텍스트 상자 컨트롤을 수락 하거나 거부 하는 사용자 입력은 선언적 구문을 지원 합니다. Mask 속성을 설정 하 여 응용 프로그램에 사용자 지정 유효성 검사 논리를 작성 하지 않고 허용 가능한 사용자 입력을 지정할 수 있습니다. 자세한 내용은 설명 부분을 참조 하십시오.는 <xref:System.Windows.Forms.MaskedTextBox> 클래스입니다.  
  
## <a name="setting-the-mask-property-manually"></a>마스크 속성을 수동으로 설정  
 마스크 속성이 지 원하는 문자에 익숙한 경우 수동으로 입력할 수 있습니다. 마스크 속성이 지 원하는 문자 요약의 설명 섹션을 참조 하십시오.는 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 속성입니다.  
  
#### <a name="to-set-the-mask-property-manually"></a>마스크 속성을 수동으로 설정 하려면  
  
1.  **디자인** 뷰의 <xref:System.Windows.Forms.MaskedTextBox>합니다.  
  
2.  에 **속성** 창을 찾습니다는 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 속성입니다.  
  
3.  마스크를 입력 합니다. 예를 들어 입력 `###`합니다.  
  
## <a name="using-the-input-mask-dialog-box"></a>입력된 마스크 대화 상자를 사용 하 여  
 입력 마스크 대화 상자에서 몇 가지 미리 정의 된 입력된 마스크를 제공합니다. 미리 정의 된 마스크를 변경 하거나 사용자가 직접 마스크를 수동으로 입력 수도 있습니다.  
  
#### <a name="to-open-the-input-mask-dialog-box"></a>입력 마스크 대화 상자를 열려면  
  
1.  **디자인** 뷰의 <xref:System.Windows.Forms.MaskedTextBox>합니다.  
  
    1.  스마트 태그를 열려면 클릭는 **MaskedTextBox 작업** 패널입니다.  
  
    2.  클릭 **마스크 설정**합니다.  
  
     \- 또는 -  
  
    1.  에 **속성** 창에서는 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 속성입니다.  
  
    2.  속성 값 열에서 줄임표 단추를 클릭 합니다.  
  
     **입력 마스크** 대화 상자가 나타납니다.  
  
#### <a name="to-use-the-input-mask-dialog-box"></a>입력 마스크 대화 상자를 사용 하려면  
  
1.  (선택 사항) 목록에 미리 정의 된 마스크 중 하나를 클릭 합니다.  
  
2.  (선택 사항) 미리 정의 된 마스크를 편집는 **마스크** 상자입니다.  
  
3.  (선택 사항) 에 새 마스크를 입력의 **마스크** 상자입니다. 즉, 미리 정의 된 마스크 중 하나를 사용할 필요가 없습니다.  
  
    > [!NOTE]
    >  미리 보기 상자 표시에서 사용자에 게 표시 하는 문자는 <xref:System.Windows.Forms.MaskedTextBox>합니다. 이러한 문자는 데이터를 올바르게 입력 사용자를 데 도움이 되도록 안내 합니다.  
  
4.  선택 하거나 선택 취소 된 **사용 ValidatingType** 확인란 합니다. **사용 ValidatingType** 확인란 사용자가 데이터 입력을 확인 하는 데이터 형식 사용 여부를 지정 합니다. 자세한 내용은 <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> 속성을 참조하세요.  
  
5.  **확인**을 클릭합니다.  
  
     / / 마스크에 입력 되는 **마스크** 속성에는 **속성** 창.  
  
## <a name="see-also"></a>참고 항목  
 [연습: MaskedTextBox 컨트롤 사용](../../../../docs/framework/winforms/controls/walkthrough-working-with-the-maskedtextbox-control.md)
