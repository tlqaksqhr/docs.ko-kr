---
title: "&lt;see&gt;(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 959da56269081ebee036c620e535185609c5bff3
ms.sourcegitcommit: c3ebb11a66e85a465c9ba2c42592222630b7ff9e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="ltseegt-c-programming-guide"></a>&lt;see&gt;(C# 프로그래밍 가이드)
## <a name="syntax"></a>구문  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a>매개 변수  
 cref = " `member`"  
 현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다. 컴파일러는 지정된 코드 요소가 있고 출력 XML의 요소 이름에 `member`를 전달하는지 확인합니다. 큰따옴표(“ ”) 안에 *멤버*를 넣습니다.  
  
## <a name="remarks"></a>설명  
 \<see> 태그를 사용하면 텍스트 내부에서 링크를 지정할 수 있습니다. 참고 항목 부분에 배치할 텍스트를 지정하려면 [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md)를 사용합니다. 코드 요소의 문서 페이지에 대한 내부 하이퍼링크를 만들려면 [cref 특성](../../../csharp/programming-guide/xmldoc/cref-attribute.md)을 사용합니다.  
  
 [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
 다음 예제에서는 요약 섹션의 \<see> 태그를 보여 줍니다.  
  
 [!code-csharp[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
