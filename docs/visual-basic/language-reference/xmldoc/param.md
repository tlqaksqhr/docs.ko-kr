---
title: '&lt;param&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 4cb3de06d574f8b9abb3e3e11641a6ada750b56a
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42935760"
---
# <a name="ltparamgt-visual-basic"></a>&lt;param&gt; (Visual Basic)
매개 변수 이름 및 설명을 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `name`  
 메서드 매개 변수의 이름입니다. 이름을 큰따옴표(“ ”)로 묶습니다.  
  
 `description`  
 매개 변수에 대한 설명입니다.  
  
## <a name="remarks"></a>설명  
 `<param>` 태그를 메서드에 대 한 매개 변수 중 하나를 설명 하는 메서드 선언의 주석에서 사용 해야 합니다.  
  
 에 대 한 텍스트는 `<param>` 태그는 다음 위치에 표시 됩니다.  
  
-   IntelliSense의 매개 변수 정보입니다. 자세한 내용은 [IntelliSense 사용](/visualstudio/ide/using-intellisense)을 참조하세요.  
  
-   개체 브라우저입니다. 자세한 내용은 [코드 구조 보기](/visualstudio/ide/viewing-the-structure-of-code)를 참조하세요.  
  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예  
 이 예제에서는 합니다 `<param>` 설명 하는 태그를 `id` 매개 변수입니다.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/index.md)
