---
title: "&lt;seealso&gt;(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- cref
- <seealso>
- seealso
helpviewer_keywords:
- cref [C#], see also
- seealso C# XML tag
- cref [C#]
- cross-references [C#], tags
- <seealso> C# XML tag
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 088445680375e1c1805f9fb4356fe98c730178e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltseealsogt-c-programming-guide"></a>&lt;seealso&gt;(C# 프로그래밍 가이드)
## <a name="syntax"></a>구문  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a>매개 변수  
 cref = " `member`"  
 현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다. 컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 요소 이름에 전달하는지 확인합니다. `member` 는 큰따옴표(“ ”)로 묶어야 합니다.  
  
 제네릭 형식에 대한 cref 참조를 만드는 방법에 대한 자세한 내용은 [\<see>](../../../csharp/programming-guide/xmldoc/see.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 \<seealso> 태그를 사용하면 참고 항목 섹션에 표시할 텍스트를 지정할 수 있습니다. 텍스트 내에서 링크를 지정하려면 [\<see>](../../../csharp/programming-guide/xmldoc/see.md)를 사용합니다.  
  
 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  
 \<seealso>를 사용한 예제는 [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
