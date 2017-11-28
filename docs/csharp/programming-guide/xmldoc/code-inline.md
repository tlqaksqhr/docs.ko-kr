---
title: "&lt;c&gt;(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 21c7830c03b0b93e3597835954ac9e7d2feb49e9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltcgt-c-programming-guide"></a>&lt;c&gt;(C# 프로그래밍 가이드)
## <a name="syntax"></a>구문  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `text`  
 코드로 표시하려는 텍스트입니다.  
  
## <a name="remarks"></a>설명  
 \<c> 태그를 사용하면 설명 내의 텍스트를 코드로 표시해야 함을 지정할 수 있습니다. 여러 줄을 코드로 지정하려면 [\<code>](../../../csharp/programming-guide/xmldoc/code.md)를 사용합니다.  
  
 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[csProgGuideDocComments#2](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/code-inline_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
