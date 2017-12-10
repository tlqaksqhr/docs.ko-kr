---
title: "방법: C + + 공용 구조체 (Visual Basic) 특성을 사용 하 여 만들기"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9352a7e4-c0da-4d07-aa14-55ed43736fcb
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bcb5291737a9f4763f680daaf625c58d308423f8
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2017
---
# <a name="how-to-create-a-cc-union-by-using-attributes-visual-basic"></a><span data-ttu-id="6109c-102">방법: 특성 (Visual Basic)를 사용 하 여 C/c + + 공용 구조체 만들기</span><span class="sxs-lookup"><span data-stu-id="6109c-102">How to: Create a C/C++ Union by Using Attributes (Visual Basic)</span></span>
<span data-ttu-id="6109c-103">특성을 사용하면 메모리에서 구조체가 레이아웃되는 방식을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6109c-103">By using attributes you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="6109c-104">예를 들어 `StructLayout(LayoutKind.Explicit)` 및 `FieldOffset` 특성을 사용하여 C/C++에서 공용 구조체로 알려진 항목을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6109c-104">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6109c-105">예제</span><span class="sxs-lookup"><span data-stu-id="6109c-105">Example</span></span>  
 <span data-ttu-id="6109c-106">이 코드 세그먼트에서 `TestUnion`의 모든 필드는 메모리의 같은 위치에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6109c-106">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="6109c-107">예제</span><span class="sxs-lookup"><span data-stu-id="6109c-107">Example</span></span>  
 <span data-ttu-id="6109c-108">다음은 명시적으로 설정된 다른 위치에서 필드가 시작하는 또 다른 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="6109c-108">The following is another example where fields start at different explicitly set locations.</span></span>  
  
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
  
 <span data-ttu-id="6109c-109">두 개의 정수 필드 `i1` 및 `i2`는 `lg`와 동일한 메모리 위치를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="6109c-109">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="6109c-110">구조체 레이아웃에 대한 이러한 종류의 제어는 플랫폼 호출을 사용할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="6109c-110">This sort of control over struct layout is useful when using platform invocation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6109c-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6109c-111">See Also</span></span>  
 <xref:System.Reflection>  
 <xref:System.Attribute>  
 [<span data-ttu-id="6109c-112">Visual Basic 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="6109c-112">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)  
 [<span data-ttu-id="6109c-113">특성</span><span class="sxs-lookup"><span data-stu-id="6109c-113">Attributes</span></span>](../../../../../docs/standard/attributes/index.md)  
 [<span data-ttu-id="6109c-114">리플렉션(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6109c-114">Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/reflection.md)  
 [<span data-ttu-id="6109c-115">특성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6109c-115">Attributes (Visual Basic)</span></span>](../../../../visual-basic/language-reference/attributes.md)  
 [<span data-ttu-id="6109c-116">사용자 지정 특성 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6109c-116">Creating Custom Attributes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [<span data-ttu-id="6109c-117">리플렉션을 사용하여 특성 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6109c-117">Accessing Attributes by Using Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
