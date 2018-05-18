---
title: '&lt;paramref&gt;(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: 0b0d49b90e097e23d3878281f9accda14b057720
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ltparamrefgt-c-programming-guide"></a>&lt;paramref&gt;(C# 프로그래밍 가이드)
## <a name="syntax"></a>구문  
  
```xml  
<paramref name="name"/>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `name`  
 참조할 매개 변수의 이름입니다. 이름을 큰따옴표(“ ”)로 묶습니다.  
  
## <a name="remarks"></a>설명  
 \<paramref> 태그를 사용하면 \<summary>, \<remarks> 블록 등의 코드 주석에 포함된 단어가 매개 변수를 참조함을 나타낼 수 있습니다. XML 파일을 처리하여 굵게, 기울임꼴 글꼴 등의 고유한 방식으로 이 단어에 서식을 지정할 수 있습니다.  
  
 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예  
 [!code-csharp[csProgGuideDocComments#7](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/paramref_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
