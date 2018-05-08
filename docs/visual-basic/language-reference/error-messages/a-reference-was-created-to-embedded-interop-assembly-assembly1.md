---
title: 포함 된 interop 어셈블리 참조를 만들었습니다. &#39; &lt;assembly1&gt; &#39; 어셈블리에서 해당 어셈블리에 간접 참조 &#39; &lt;assembly2&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc40059
- bc40059
helpviewer_keywords:
- VBC40059
- BC40059
ms.assetid: 520e39cb-8ab6-46f5-aa00-08afd51b4b7c
ms.openlocfilehash: 43a441b6b99988ae1b47969dde9c4bc815820767
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="a-reference-was-created-to-embedded-interop-assembly-39ltassembly1gt39-because-of-an-indirect-reference-to-that-assembly-from-assembly-39ltassembly2gt39"></a>포함 된 interop 어셈블리 참조를 만들었습니다. &#39; &lt;assembly1&gt; &#39; 어셈블리에서 해당 어셈블리에 간접 참조 &#39; &lt;assembly2&gt;&#39;
포함된 interop 어셈블리 ‘\<assembly1>’에 대한 참조는 해당 어셈블리에 대한 ‘\<assembly2>’ 어셈블리의 간접 참조로 인해 만들어졌습니다. 두 어셈블리 중 하나에서 ‘Embed Interop Types’ 속성을 변경하는 것이 좋습니다.  
  
 `Embed Interop Types` 속성이 `True`로 설정된 어셈블리(assembly1)에 대한 참조를 추가했습니다. 이는 해당 어셈블리의 interop 형식 정보를 포함하도록 컴파일러에 지시합니다. 그러나 참조한 다른 어셈블리(assembly2)에서도 해당 어셈블리(assembly1)를 참조하고 `Embed Interop Types` 속성을 `False`로 설정했으므로 컴파일러에서 해당 어셈블리의 interop 형식 정보를 포함할 수 없습니다.  
  
> [!NOTE]
>  어셈블리 참조에서 `Embed Interop Types` 속성을 `True`로 설정하는 것은 명령줄 컴파일러에 대해 `/link` 옵션을 사용하여 해당 어셈블리를 참조하는 것과 같습니다.  
  
 **오류 ID:** BC40059  
  
### <a name="to-address-this-warning"></a>이 경고를 해결하려면  
  
-   두 어셈블리의 interop 형식 정보를 포함하려면 assembly1에 대한 모든 참조에서 `Embed Interop Types` 속성을 `True`로 설정하세요.  
  
-   경고를 제거하기 위해 assembly1의 `Embed Interop Types` 속성을 `False`로 설정할 수 있습니다. 이 경우 interop 형식 정보는 주 interop 어셈블리 (PIA)에서 제공 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [/link(Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md)  
 [비관리 코드와의 상호 운용](../../../framework/interop/index.md)
