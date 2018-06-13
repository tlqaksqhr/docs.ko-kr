---
title: My.Forms 및 My.WebServices에서 제공하는 기본 개체 인스턴스(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: 421995684201ec48d5e8aff9b0ed7640efd1e4b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582664"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a>My.Forms 및 My.WebServices에서 제공하는 기본 개체 인스턴스(Visual Basic)
[My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) 및 [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) 개체 폼, 데이터 원본 및 응용 프로그램에서 사용 하는 XML 웹 서비스에 대 한 액세스를 제공 합니다. 컬렉션을 제공 하 여이 수행 *인스턴스를 기본* 이러한 각 개체의 합니다.  
  
## <a name="default-instances"></a>기본 인스턴스  
 기본 인스턴스 수 하지 않아도 런타임에서 제공 하는 클래스의 인스턴스가 선언 되었고 사용 하 여 인스턴스화될는 `Dim` 및 `New` 문. 다음 예제에서는 방법을 있습니다 선언 하 고의 인스턴스를 인스턴스화할는 <xref:System.Windows.Forms.Form> 라는 클래스 `Form1`, 어떻게 현재 위치는이 기본 인스턴스를 가져올 수 및 <xref:System.Windows.Forms.Form> 클래스를 통해 `My.Forms`합니다.  
  
 [!code-vb[VbVbcnMy#5](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_1.vb)]  
  
 [!code-vb[VbVbcnMy#6](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_2.vb)]  
  
 `My.Forms` 의 기본 인스턴스 컬렉션을 반환 하는 개체 마다 `Form` 프로젝트에 있는 클래스입니다. 마찬가지로, `My.WebServices` 응용 프로그램에 대 한 참조를 만든 모든 웹 서비스에 대 한 프록시 클래스의 기본 인스턴스를 제공 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [My.Forms 개체](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [My.WebServices 개체](../../../visual-basic/language-reference/objects/my-webservices-object.md)  
 [My가 프로젝트 형식에 의존하는 방식](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
