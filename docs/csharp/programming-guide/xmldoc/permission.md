---
title: "&lt;permission&gt;(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 37bb37ea14edc1f91225f9b04b18b354d99579b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltpermissiongt-c-programming-guide"></a>&lt;permission&gt;(C# 프로그래밍 가이드)
## <a name="syntax"></a>구문  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a>매개 변수  
 cref = " `member`"  
 현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다. 컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 정식 요소 이름으로 변환하는지 확인합니다. *member*는 큰따옴표(“ ”)로 묶어야 합니다.  
  
 제네릭 형식에 대한 cref 참조를 만드는 방법에 대한 자세한 내용은 [\<see>](../../../csharp/programming-guide/xmldoc/see.md)를 참조하세요.  
  
 `description`  
 멤버 액세스 권한에 대한 설명입니다.  
  
## <a name="remarks"></a>설명  
 \<permission> 태그를 사용하면 멤버 액세스 권한을 문서화할 수 있습니다. <xref:System.Security.PermissionSet> 클래스를 사용하면 멤버 액세스 권한을 지정할 수 있습니다.  
  
 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[csProgGuideDocComments#8](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/permission_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
