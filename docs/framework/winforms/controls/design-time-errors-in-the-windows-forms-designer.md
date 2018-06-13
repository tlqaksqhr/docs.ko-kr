---
title: Windows Forms 디자이너의 디자인 타임 오류
ms.date: 03/30/2017
f1_keywords:
- DTELErrorList
- WhyDTELPage
helpviewer_keywords:
- errors [Windows Forms Designer]
- design-time errors [Windows Forms Designer]
ms.assetid: ad408380-825a-46d8-9a4a-531b130b88ce
ms.openlocfilehash: 00296b51563a5f973b8e5d64c55867568ff0324e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527789"
---
# <a name="design-time-errors-in-the-windows-forms-designer"></a>Windows Forms 디자이너의 디자인 타임 오류
이 문서에서는 Windows Forms 디자이너를 로드하지 못할 때 Microsoft Visual Studio에 표시되는 디자인 타임 오류 목록의 의미와 용도에 대해 설명합니다. 이 오류 목록이 표시되면 디자이너에서 버그가 아닌 코드의 오류를 수정하는 보조 기능으로 해석해야 합니다.  
  
 이 오류 목록의 기본적인 이해를 통해 오류에 대한 자세한 정보를 제공하고 가능한 해결 방법을 제안하여 응용 프로그램을 디버깅할 수 있습니다.  
  
## <a name="the-design-time-error-list-interface"></a>디자인 타임 오류 목록 인터페이스  
 Windows Forms 디자이너를 로드하지 못하는 경우 오류 목록이 디자이너에 표시됩니다. 오류는 범주로 그룹화됩니다. 예를 들어 선언되지 않은 변수의 네 가지 인스턴스가 있는 경우 동일한 오류 범주로 그룹화됩니다. 각 오류 범주는 해당 오류를 요약한 간단한 설명을 포함합니다.  
  
 오류 범주 머리글을 클릭하거나 확장/축소 펼침 단추를 클릭하여 오류 범주를 확장하거나 축소할 수 있습니다. 오류 범주를 확장하면 다음과 같은 추가 도움말이 표시됩니다.  
  
-   이 오류의 인스턴스  
  
-   이 오류에 대한 도움말  
  
-   이 오류에 대한 포럼 게시물  
  
### <a name="instances-of-this-error"></a>이 오류의 인스턴스  
 추가 도움말은 현재 프로젝트에서 오류 메시지의 모든 인스턴스를 나열합니다. 대부분의 오류는 다음과 같은 형식으로 정확한 위치를 포함합니다. *[프로젝트 이름]* *[양식 이름]* 줄:*[줄 번호]* 열:*[열 번호]* **코드로 이동** 링크를 통해 오류가 발생하는 코드의 위치로 이동합니다.  
  
 호출 스택이 오류와 연결되는 경우 **호출 스택 표시** 링크를 클릭하면 오류를 더 확장하여 호출 스택을 표시할 수 있습니다. 스택 검사는 중요한 디버깅 정보를 제공할 수 있습니다. 예를 들어 오류가 발생하기 전에 호출된 함수를 추적할 수 있습니다. 호출 스택은 선택하여 복사하고 저장할 수 있습니다.  
  
> [!NOTE]
>  Visual Basic에서 디자인 타임 오류 목록은 둘 이상의 오류를 표시하지 않지만 동일한 오류의 여러 인스턴스를 표시할 수 있습니다. Visual C++에서 오류에는 이동 코드 링크/줄 번호 링크가 없습니다.  
  
### <a name="help-with-this-error"></a>이 오류에 대한 도움말  
 이 오류에 관련된 MSDN 도움말 항목에 대한 링크가 포함되는 경우 추가 도움말은 도움말 항목에 대한 링크를 포함합니다. 링크를 클릭하면 Visual Studio에 관련된 도움말 항목이 나타납니다.  
  
### <a name="forum-posts-about-this-error"></a>이 오류에 대한 포럼 게시물  
 추가 도움말은 오류와 관련된 MSDN 포럼 게시물에 대한 링크를 포함합니다. 포럼은 오류 메시지의 문자열에 따라 검색됩니다. 다음과 같은 포럼을 검색하도록 시도할 수 있습니다.  
  
-   [Windows Forms 디자이너 포럼](http://go.microsoft.com/fwlink/?LinkId=203524)  
  
-   [Windows Forms 포럼](http://go.microsoft.com/fwlink/?LinkId=203523)  
  
### <a name="ignore-and-continue"></a>무시 후 계속  
 오류 상태를 무시하고 디자이너를 계속 로드할 수 있습니다. 이 작업을 선택하면 예기치 않은 동작이 발생할 수 있습니다. 예를 들어 컨트롤이 디자인 화면에 표시되지 않을 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [디자인 타임 개발 문제 해결](http://msdn.microsoft.com/library/e048d08e-fa7c-4be8-b238-4abaa199a0a6)  
 [컨트롤 및 구성 요소 제작 문제 해결](../../../../docs/framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 [디자인 타임에 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [Windows Forms 디자이너 오류 메시지](http://msdn.microsoft.com/library/cf610bf4-5fe4-471c-bce7-6a05ece07bd2)
