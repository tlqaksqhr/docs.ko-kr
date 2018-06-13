---
title: 시작 폼이 지정되지 않았습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
ms.openlocfilehash: 699d20e6afb2335336b3652be5907f0dd72299fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586788"
---
# <a name="a-startup-form-has-not-been-specified"></a>시작 폼이 지정되지 않았습니다.
응용 프로그램 사용은 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> 클래스 하지만 시작 폼을 지정 하지 않습니다.  
  
 때문일 수 있습니다는 **응용 프로그램 프레임 워크 사용** 프로젝트 디자이너에서 확인란을 선택 하지만 **시작 폼** 지정 되지 않았습니다. 자세한 내용은 [프로젝트 디자이너, 응용 프로그램 페이지(Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)를 참조하세요.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  응용 프로그램에 대 한 시작 개체를 지정 합니다.  
  
     자세한 내용은 [프로젝트 디자이너, 응용 프로그램 페이지(Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)를 참조하세요.  
  
2.  재정의 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> 설정 하는 메서드는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> 속성 시작 폼을 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>  
 [Visual Basic 응용 프로그램 모델 개요](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
