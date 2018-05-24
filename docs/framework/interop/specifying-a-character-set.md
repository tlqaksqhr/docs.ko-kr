---
title: 문자 집합 지정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- platform invoke, attribute fields
- attribute fields in platform invoke, CharSet
- CharSet field
ms.assetid: a8347eb1-295f-46b9-8a78-63331f9ecc50
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1016a0c63a85919764271e01771ff8192341725c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="specifying-a-character-set"></a><span data-ttu-id="7ca80-102">문자 집합 지정</span><span class="sxs-lookup"><span data-stu-id="7ca80-102">Specifying a Character Set</span></span>
<span data-ttu-id="7ca80-103"><xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 필드는 문자열 마샬링을 제어하고 플랫폼 호출이 DLL에서 함수 이름을 찾는 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-103">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field controls string marshaling and determines how platform invoke finds function names in a DLL.</span></span> <span data-ttu-id="7ca80-104">이 항목에서는 두 동작에 대해 모두 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-104">This topic describes both behaviors.</span></span>  
  
 <span data-ttu-id="7ca80-105">일부 API는 문자열 인수를 사용하는 함수의 두 가지 버전인 narrow(ANSI) 및 wide(Unicode)를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-105">Some APIs export two versions of functions that take string arguments: narrow (ANSI) and wide (Unicode).</span></span> <span data-ttu-id="7ca80-106">예를 들어 Win32 API에는 **MessageBox** 함수에 대한 다음 진입점 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-106">The Win32 API, for instance, includes the following entry-point names for the **MessageBox** function:</span></span>  
  
-   <span data-ttu-id="7ca80-107">**MessageBoxA**</span><span class="sxs-lookup"><span data-stu-id="7ca80-107">**MessageBoxA**</span></span>  
  
     <span data-ttu-id="7ca80-108">진입점 이름에 “A”를 추가하여 구분되는 1바이트 문자 ANSI 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-108">Provides 1-byte character ANSI formatting, distinguished by an "A" appended to the entry-point name.</span></span> <span data-ttu-id="7ca80-109">**MessageBoxA** 호출은 Windows 95 및 Windows 98 플랫폼에서 일반적인 경우와 마찬가지로 항상 문자열을 ANSI 형식으로 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-109">Calls to **MessageBoxA** always marshal strings in ANSI format, as is common on Windows 95 and Windows 98 platforms.</span></span>  
  
-   <span data-ttu-id="7ca80-110">**MessageBoxW**</span><span class="sxs-lookup"><span data-stu-id="7ca80-110">**MessageBoxW**</span></span>  
  
     <span data-ttu-id="7ca80-111">진입점 이름에 “W”를 추가하여 구분되는 2바이트 문자 유니코드 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-111">Provides 2-byte character Unicode formatting, distinguished by a "W" appended to the entry-point name.</span></span> <span data-ttu-id="7ca80-112">**MessageBoxW** 호출은 Windows NT, Windows 2000 및 Windows XP 플랫폼에서 일반적인 경우와 마찬가지로 항상 문자열을 유니코드 형식으로 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-112">Calls to **MessageBoxW** always marshal strings in Unicode format, as is common on Windows NT, Windows 2000, and Windows XP platforms.</span></span>  
  
## <a name="string-marshaling-and-name-matching"></a><span data-ttu-id="7ca80-113">문자열 마샬링 및 이름 일치</span><span class="sxs-lookup"><span data-stu-id="7ca80-113">String Marshaling and Name Matching</span></span>  
 <span data-ttu-id="7ca80-114">**CharSet** 필드는 다음 값을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-114">The **CharSet** field accepts the following values:</span></span>  
  
 <span data-ttu-id="7ca80-115">**CharSet.Ansi**(기본값)</span><span class="sxs-lookup"><span data-stu-id="7ca80-115">**CharSet.Ansi** (default value)</span></span>  
  
-   <span data-ttu-id="7ca80-116">문자열 마샬링</span><span class="sxs-lookup"><span data-stu-id="7ca80-116">String marshaling</span></span>  
  
     <span data-ttu-id="7ca80-117">플랫폼 호출은 관리되는 형식(유니코드)의 문자열을 ANSI 형식으로 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-117">Platform invoke marshals strings from their managed format (Unicode) to ANSI format.</span></span>  
  
-   <span data-ttu-id="7ca80-118">이름 일치</span><span class="sxs-lookup"><span data-stu-id="7ca80-118">Name matching</span></span>  
  
     <span data-ttu-id="7ca80-119"><xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> 필드가 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]의 기본값인 **true**이면 플랫폼 호출이 지정한 이름만 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-119">When the <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> field is **true**, as it is by default in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="7ca80-120">예를 들어 **MessageBox**를 지정하는 경우 플랫폼 호출은 **MessageBox**를 검색하고, 정확한 철자를 찾을 수 없으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-120">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails when it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="7ca80-121">**ExactSpelling** 필드가 C++ 및 C#의 기본값인 **false**이면 플랫폼 호출은 올바른 별칭(**MessageBox**)을 먼저 검색한 다음, 올바른 별칭을 찾을 수 없는 경우 잘못된 이름(**MessageBoxA**)을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-121">When the **ExactSpelling** field is **false**, as it is by default in C++ and C#, platform invoke searches for the unmangled alias first (**MessageBox**), then the mangled name (**MessageBoxA**) if the unmangled alias is not found.</span></span> <span data-ttu-id="7ca80-122">ANSI 이름 일치 동작은 유니코드 이름 일치 동작과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-122">Notice that ANSI name-matching behavior differs from Unicode name-matching behavior.</span></span>  
  
 <span data-ttu-id="7ca80-123">**CharSet.Unicode**</span><span class="sxs-lookup"><span data-stu-id="7ca80-123">**CharSet.Unicode**</span></span>  
  
-   <span data-ttu-id="7ca80-124">문자열 마샬링</span><span class="sxs-lookup"><span data-stu-id="7ca80-124">String marshaling</span></span>  
  
     <span data-ttu-id="7ca80-125">플랫폼 호출은 관리되는 형식(유니코드)의 문자열을 유니코드 형식으로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-125">Platform invoke copies strings from their managed format (Unicode) to Unicode format.</span></span>  
  
-   <span data-ttu-id="7ca80-126">이름 일치</span><span class="sxs-lookup"><span data-stu-id="7ca80-126">Name matching</span></span>  
  
     <span data-ttu-id="7ca80-127">**ExactSpelling** 필드가 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]의 기본값인 **true**이면 플랫폼 호출이 지정한 이름만 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-127">When the **ExactSpelling** field is **true**, as it is by default in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="7ca80-128">예를 들어 **MessageBox**를 지정하는 경우 플랫폼 호출은 **MessageBox**를 검색하고, 정확한 철자를 찾을 수 없으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-128">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails if it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="7ca80-129">**ExactSpelling** 필드가 C++ 및 C#의 기본값인 **false**이면 플랫폼 호출은 잘못된 이름(**MessageBoxW**)을 먼저 검색한 다음, 잘못된 이름을 찾을 수 없는 경우 올바른 별칭(**MessageBox**)을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-129">When the **ExactSpelling** field is **false**, as it is by default in C++ and C#, platform invoke searches for the mangled name first (**MessageBoxW**), then the unmangled alias (**MessageBox**) if the mangled name is not found.</span></span> <span data-ttu-id="7ca80-130">유니코드 이름 일치 동작은 ANSI 이름 일치 동작과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-130">Notice that Unicode name-matching behavior differs from ANSI name-matching behavior.</span></span>  
  
 <span data-ttu-id="7ca80-131">**CharSet.Auto**</span><span class="sxs-lookup"><span data-stu-id="7ca80-131">**CharSet.Auto**</span></span>  
  
-   <span data-ttu-id="7ca80-132">플랫폼 호출이 대상 플랫폼에 따라 런타임에 ANSI와 유니코드 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-132">Platform invoke chooses between ANSI and Unicode formats at run time, based on the target platform.</span></span>  
  
## <a name="specifying-a-character-set-in-visual-basic"></a><span data-ttu-id="7ca80-133">Visual Basic에서 문자 집합 지정</span><span class="sxs-lookup"><span data-stu-id="7ca80-133">Specifying a Character Set in Visual Basic</span></span>  
 <span data-ttu-id="7ca80-134">다음 예제에서는 매번 서로 다른 문자 집합 동작을 사용하여 **MessageBox** 함수를 세 번 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-134">The following example declares the **MessageBox** function three times, each time with different character-set behavior.</span></span> <span data-ttu-id="7ca80-135">**Ansi**, **유니코드** 또는 **자동** 키워드를 선언문에 추가하여 Visual Basic에서 문자 집합 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-135">You can specify character-set behavior in Visual Basic by adding the **Ansi**, **Unicode**, or **Auto** keyword to the declaration statement.</span></span>  
  
 <span data-ttu-id="7ca80-136">첫 번째 선언문과 같이 문자 집합 키워드를 생략하면 <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 필드는 기본적으로 ANSI 문자 집합으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-136">If you omit the character-set keyword, as is done in the first declaration statement, the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field defaults to the ANSI character set.</span></span> <span data-ttu-id="7ca80-137">예제에서 두 번째 문과 세 번째 문은 키워드를 사용해서 명시적으로 문자 집합을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-137">The second and third statements in the example explicitly specify a character set with a keyword.</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
   Declare Function MessageBoxA Lib "user32.dll"(ByVal hWnd As Integer, _  
       ByVal txt As String, ByVal caption As String, _  
       ByVal Typ As Integer) As Integer  
  
   Declare Unicode Function MessageBoxW Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
        ByVal caption As String, ByVal Typ As Integer) As Integer  
  
   Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
        ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
## <a name="specifying-a-character-set-in-c-and-c"></a><span data-ttu-id="7ca80-138">C# 및 C++에서 문자 집합 지정</span><span class="sxs-lookup"><span data-stu-id="7ca80-138">Specifying a Character Set in C# and C++</span></span>  
 <span data-ttu-id="7ca80-139"><xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 필드는 기본 문자 집합을 ANSI 또는 유니코드로 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-139">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field identifies the underlying character set as ANSI or Unicode.</span></span> <span data-ttu-id="7ca80-140">문자 집합은 메서드에 대한 문자열 인수를 마샬링하는 방법을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-140">The character set controls how string arguments to a method should be marshaled.</span></span> <span data-ttu-id="7ca80-141">다음 형식 중 하나를 사용하여 문자 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-141">Use one of the following forms to indicate the character set:</span></span>  
  
```csharp  
[DllImport("dllname", CharSet=CharSet.Ansi)]  
[DllImport("dllname", CharSet=CharSet.Unicode)]  
[DllImport("dllname", CharSet=CharSet.Auto)]  
```  
  
```cpp  
[DllImport("dllname", CharSet=CharSet::Ansi)]  
[DllImport("dllname", CharSet=CharSet::Unicode)]  
[DllImport("dllname", CharSet=CharSet::Auto)]  
```  
  
 <span data-ttu-id="7ca80-142">다음 예제에서는 문자 집합을 지정하는 **MessageBox** 함수의 세 가지 관리되는 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-142">The following example shows three managed definitions of the **MessageBox** function attributed to specify a character set.</span></span> <span data-ttu-id="7ca80-143">첫 번째 정의에서는 생략에 의해 **CharSet** 필드가 기본값인 ANSI 문자 집합으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ca80-143">In the first definition, by its omission, the **CharSet** field defaults to the ANSI character set.</span></span>  
  
```csharp  
[DllImport("user32.dll")]  
    public static extern int MessageBoxA(int hWnd, String text,   
        String caption, uint type);  
[DllImport("user32.dll", CharSet=CharSet.Unicode)]  
    public static extern int MessageBoxW(int hWnd, String text,   
        String caption, uint type);  
[DllImport("user32.dll", CharSet=CharSet.Auto)]  
    public static extern int MessageBox(int hWnd, String text,   
        String caption, uint type);  
```  
  
```cpp  
typedef void* HWND;  
  
//Can use MessageBox or MessageBoxA.  
[DllImport("user32")]  
extern "C" int MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
  
//Can use MessageBox or MessageBoxW.  
[DllImport("user32", CharSet=CharSet::Unicode)]  
extern "C" int MessageBoxW(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
  
//Must use MessageBox.  
[DllImport("user32", CharSet=CharSet::Auto)]  
extern "C" int MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ca80-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ca80-144">See Also</span></span>  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 [<span data-ttu-id="7ca80-145">관리 코드에서 프로토타입 만들기</span><span class="sxs-lookup"><span data-stu-id="7ca80-145">Creating Prototypes in Managed Code</span></span>](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)  
 [<span data-ttu-id="7ca80-146">플랫폼 호출 예제</span><span class="sxs-lookup"><span data-stu-id="7ca80-146">Platform Invoke Examples</span></span>](../../../docs/framework/interop/platform-invoke-examples.md)  
 [<span data-ttu-id="7ca80-147">플랫폼 호출을 사용하여 데이터 마샬링</span><span class="sxs-lookup"><span data-stu-id="7ca80-147">Marshaling Data with Platform Invoke</span></span>](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)
