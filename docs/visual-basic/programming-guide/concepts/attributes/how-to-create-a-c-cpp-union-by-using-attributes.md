---
title: "방법: 특성 (Visual Basic)를 사용 하 여 C + + 공용 구조체 만들기 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 9352a7e4-c0da-4d07-aa14-55ed43736fcb
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 195dc0c64cb01e38ede0b7c34c30ca7912aea685
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-a-cc-union-by-using-attributes-visual-basic"></a><span data-ttu-id="6db1d-102">방법: 특성 (Visual Basic)를 사용 하 여 C/c + + 공용 구조체 만들기</span><span class="sxs-lookup"><span data-stu-id="6db1d-102">How to: Create a C/C++ Union by Using Attributes (Visual Basic)</span></span>
<span data-ttu-id="6db1d-103">특성을 사용 하 여 구조체 레이아웃 하는 방법 메모리에 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6db1d-103">By using attributes you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="6db1d-104">이것이 C/c + +에서 공용 구조체를 사용 하 여 만들 수는 예를 들어는 `StructLayout(LayoutKind.Explicit)` 및 `FieldOffset` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="6db1d-104">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6db1d-105">예제</span><span class="sxs-lookup"><span data-stu-id="6db1d-105">Example</span></span>  
 <span data-ttu-id="6db1d-106">이 코드 세그먼트의 필드를 모두에서 `TestUnion` 메모리의 같은 위치에서 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="6db1d-106">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>  
  
```vb  
' Add an Imports statement for System.Runtime.InteropServices.  
  
<System.Runtime.InteropServices.StructLayout(   
      System.Runtime.InteropServices.LayoutKind.Explicit)>   
Structure TestUnion  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public i As Integer  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public d As Double  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public c As Char  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public b As Byte  
End Structure  
```  
  
## <a name="example"></a><span data-ttu-id="6db1d-107">예제</span><span class="sxs-lookup"><span data-stu-id="6db1d-107">Example</span></span>  
 <span data-ttu-id="6db1d-108">다음은 또 다른 예 각 다른 필드의 시작 위치를 명시적으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6db1d-108">The following is another example where fields start at different explicitly set locations.</span></span>  
  
```vb  
' Add an Imports statement for System.Runtime.InteropServices.  
  
 <System.Runtime.InteropServices.StructLayout(   
      System.Runtime.InteropServices.LayoutKind.Explicit)>   
Structure TestExplicit  
     <System.Runtime.InteropServices.FieldOffset(0)>   
     Public lg As Long  
  
     <System.Runtime.InteropServices.FieldOffset(0)>   
     Public i1 As Integer  
  
     <System.Runtime.InteropServices.FieldOffset(4)>   
     Public i2 As Integer  
  
     <System.Runtime.InteropServices.FieldOffset(8)>   
     Public d As Double  
  
     <System.Runtime.InteropServices.FieldOffset(12)>   
     Public c As Char  
  
     <System.Runtime.InteropServices.FieldOffset(14)>   
     Public b As Byte  
 End Structure  
```  
  
 <span data-ttu-id="6db1d-109">두 개의 정수 필드 `i1` 및 `i2`와 동일한 메모리 위치를 공유 `lg`합니다.</span><span class="sxs-lookup"><span data-stu-id="6db1d-109">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="6db1d-110">이러한 종류의 구조체 레이아웃에 대 한 제어는 플랫폼 호출을 사용 하는 경우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6db1d-110">This sort of control over struct layout is useful when using platform invocation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6db1d-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6db1d-111">See Also</span></span>  
 <span data-ttu-id="6db1d-112"><xref:System.Reflection></xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="6db1d-112"><xref:System.Reflection></span></span>   
 <span data-ttu-id="6db1d-113"><xref:System.Attribute></xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="6db1d-113"><xref:System.Attribute></span></span>   
<span data-ttu-id="6db1d-114"> [Visual Basic 프로그래밍 가이드](../../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6db1d-114"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="6db1d-115"> [특성](https://msdn.microsoft.com/library/5x6cd29c) </span><span class="sxs-lookup"><span data-stu-id="6db1d-115"> [Attributes](https://msdn.microsoft.com/library/5x6cd29c) </span></span>  
<span data-ttu-id="6db1d-116"> [리플렉션 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="6db1d-116"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span></span>  
<span data-ttu-id="6db1d-117"> [특성 (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span><span class="sxs-lookup"><span data-stu-id="6db1d-117"> [Attributes (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span></span>  
<span data-ttu-id="6db1d-118"> [사용자 지정 특성 (Visual Basic) 만들기](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="6db1d-118"> [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) </span></span>  
<span data-ttu-id="6db1d-119"> [(Visual Basic) 리플렉션을 사용 하 여 특성 액세스](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span><span class="sxs-lookup"><span data-stu-id="6db1d-119"> [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span></span>
