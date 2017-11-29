---
title: "구조체 전달"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: platform invoke, calling unmanaged functions
ms.assetid: 9b92ac73-32b7-4e1b-862e-6d8d950cf169
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ab9002d6e86b91f0ed21dae41f82af31f04291c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="passing-structures"></a><span data-ttu-id="d38b3-102">구조체 전달</span><span class="sxs-lookup"><span data-stu-id="d38b3-102">Passing Structures</span></span>
<span data-ttu-id="d38b3-103">관리되지 않는 여러 함수에서는 함수, 구조체 멤버(Visual Basic의 사용자 정의 형식) 또는 관리 코드에 정의된 클래스 멤버에 매개 변수로 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-103">Many unmanaged functions expect you to pass, as a parameter to the function, members of structures (user-defined types in Visual Basic) or members of classes that are defined in managed code.</span></span> <span data-ttu-id="d38b3-104">플랫폼 호출을 사용하여 구조체 또는 클래스를 비관리 코드에 전달할 때 원래 레이아웃과 맞춤을 유지하기 위해 추가 정보를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-104">When passing structures or classes to unmanaged code using platform invoke, you must provide additional information to preserve the original layout and alignment.</span></span> <span data-ttu-id="d38b3-105">이 항목에서는 형식이 지정된 유형을 정의하는 데 사용하는 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-105">This topic introduces the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute, which you use to define formatted types.</span></span> <span data-ttu-id="d38b3-106">관리되는 구조체와 클래스의 경우 **LayoutKind** 열거형에서 제공하는 예측 가능한 여러 레이아웃 동작 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-106">For managed structures and classes, you can select from several predictable layout behaviors supplied by the **LayoutKind** enumeration.</span></span>  
  
 <span data-ttu-id="d38b3-107">이 항목에 제시된 개념의 핵심은 구조체와 클래스 형식 사이에 중요한 차이점이 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-107">Central to the concepts presented in this topic is an important difference between structure and class types.</span></span> <span data-ttu-id="d38b3-108">구조체는 값 형식이고 클래스는 참조 형식입니다. 클래스는 항상 한 수준 이상의 메모리 간접 참조(값에 대한 포인터)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-108">Structures are value types and classes are reference types — classes always provide at least one level of memory indirection (a pointer to a value).</span></span> <span data-ttu-id="d38b3-109">다음 표의 첫 번째 열에 있는 시그니처를 통해 표시된 대로 관리되지 않는 함수는 간접 참조를 요구하는 경우가 많으므로 이 차이점은 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-109">This difference is important because unmanaged functions often demand indirection, as shown by the signatures in the first column of the following table.</span></span> <span data-ttu-id="d38b3-110">나머지 열에 있는 클래스 선언과 관리된 구조체는 선언에서 간접 참조의 수준을 조정할 수 있는 정도를 보여 줍니다. 선언은 Visual Basic과 Visual C# 모두용으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-110">The managed structure and class declarations in the remaining columns show the degree to which you can adjust the level of indirection in your declaration.Declarations are provided for both Visual Basic and Visual C#.</span></span>  
  
|<span data-ttu-id="d38b3-111">관리되지 않는 서명</span><span class="sxs-lookup"><span data-stu-id="d38b3-111">Unmanaged signature</span></span>|<span data-ttu-id="d38b3-112">관리되는 선언:</span><span class="sxs-lookup"><span data-stu-id="d38b3-112">Managed declaration:</span></span> <br /><span data-ttu-id="d38b3-113">간접 참조가 아님</span><span class="sxs-lookup"><span data-stu-id="d38b3-113">no indirection</span></span><br />`Structure MyType`<br />`struct MyType;`|<span data-ttu-id="d38b3-114">관리되는 선언:</span><span class="sxs-lookup"><span data-stu-id="d38b3-114">Managed declaration:</span></span> <br /><span data-ttu-id="d38b3-115">한 수준의 간접 참조</span><span class="sxs-lookup"><span data-stu-id="d38b3-115">one level of indirection</span></span><br />`Class MyType`<br />`class MyType;`|  
|-------------------------|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|  
|`DoWork(MyType x);`<br /><br /> <span data-ttu-id="d38b3-116">0 수준의 간접 참조를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-116">Demands zero levels of indirection.</span></span>|`DoWork(ByVal x As MyType)` <br /> `DoWork(MyType x)`<br /><br /> <span data-ttu-id="d38b3-117">0 수준의 간접 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-117">Adds zero levels of indirection.</span></span>|<span data-ttu-id="d38b3-118">이미 한 수준의 간접 참조가 있으므로 가능하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-118">Not possible because there is already one level of indirection.</span></span>|  
|`DoWork(MyType* x);`<br /><br /> <span data-ttu-id="d38b3-119">한 수준의 간접 참조를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-119">Demands one level of indirection.</span></span>|`DoWork(ByRef x As MyType)` <br /> `DoWork(ref MyType x)`<br /><br /> <span data-ttu-id="d38b3-120">한 수준의 간접 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-120">Adds one level of indirection.</span></span>|`DoWork(ByVal x As MyType)` <br /> `DoWork(MyType x)`<br /><br /> <span data-ttu-id="d38b3-121">0 수준의 간접 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-121">Adds zero levels of indirection.</span></span>|  
|`DoWork(MyType** x);`<br /><br /> <span data-ttu-id="d38b3-122">두 수준의 간접 참조를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-122">Demands two levels of indirection.</span></span>|<span data-ttu-id="d38b3-123">**ByRef** **ByRef** 또는 `ref` `ref`는 사용할 수 없기 때문에 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-123">Not possible because **ByRef** **ByRef** or `ref` `ref` cannot be used.</span></span>|`DoWork(ByRef x As MyType)` <br /> `DoWork(ref MyType x)`<br /><br /> <span data-ttu-id="d38b3-124">한 수준의 간접 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-124">Adds one level of indirection.</span></span>|  
  
 <span data-ttu-id="d38b3-125">이 표에서는 플랫폼 호출 선언에 대한 다음과 같은 지침을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-125">The table describes the following guidelines for platform invoke declarations:</span></span>  
  
-   <span data-ttu-id="d38b3-126">관리되지 않는 함수에서 간접 참조를 요구하지 않는 경우 값 형식으로 전달된 구조체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-126">Use a structure passed by value when the unmanaged function demands no indirection.</span></span>  
  
-   <span data-ttu-id="d38b3-127">관리되지 않는 함수에서 한 수준의 간접 참조를 요구하는 경우 참조 형식으로 전달된 구조체 또는 값 형식으로 전달된 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-127">Use either a structure passed by reference or a class passed by value when the unmanaged function demands one level of indirection.</span></span>  
  
-   <span data-ttu-id="d38b3-128">관리되지 않는 함수에서 두 수준의 간접 참조를 요구하는 경우 참조 형식으로 전달된 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-128">Use a class passed by reference when the unmanaged function demands two levels of indirection.</span></span>  
  
## <a name="declaring-and-passing-structures"></a><span data-ttu-id="d38b3-129">구조체 선언 및 전달</span><span class="sxs-lookup"><span data-stu-id="d38b3-129">Declaring and Passing Structures</span></span>  
 <span data-ttu-id="d38b3-130">다음 예제에서는 관리 코드에서 `Point` 및 `Rect` 구조체를 정의하고, User32.dll 파일의 **PtInRect** 함수에 매개 변수로 형식을 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-130">The following example shows how to define the `Point` and `Rect` structures in managed code, and pass the types as parameter to the **PtInRect** function in the User32.dll file.</span></span> <span data-ttu-id="d38b3-131">**PtInRect**에는 다음과 같은 관리되지 않은 시그니처가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-131">**PtInRect** has the following unmanaged signature:</span></span>  
  
```  
BOOL PtInRect(const RECT *lprc, POINT pt);  
```  
  
 <span data-ttu-id="d38b3-132">함수에는 RECT 형식에 대한 포인터가 있어야 하므로 참조 형식으로 Rect 구조체를 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-132">Notice that you must pass the Rect structure by reference, since the function expects a pointer to a RECT type.</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
  
<StructLayout(LayoutKind.Sequential)> Public Structure Point  
    Public x As Integer  
    Public y As Integer  
End Structure  
  
Public Structure <StructLayout(LayoutKind.Explicit)> Rect  
    <FieldOffset(0)> Public left As Integer  
    <FieldOffset(4)> Public top As Integer  
    <FieldOffset(8)> Public right As Integer  
    <FieldOffset(12)> Public bottom As Integer  
End Structure  
  
Class Win32API      
    Declare Auto Function PtInRect Lib "user32.dll" _  
    (ByRef r As Rect, p As Point) As Boolean  
End Class  
```  
  
```csharp  
using System.Runtime.InteropServices;  
  
[StructLayout(LayoutKind.Sequential)]  
public struct Point {  
    public int x;  
    public int y;  
}     
  
[StructLayout(LayoutKind.Explicit)]  
public struct Rect {  
    [FieldOffset(0)] public int left;  
    [FieldOffset(4)] public int top;  
    [FieldOffset(8)] public int right;  
    [FieldOffset(12)] public int bottom;  
}     
  
class Win32API {  
    [DllImport("User32.dll")]  
    public static extern bool PtInRect(ref Rect r, Point p);  
}  
```  
  
## <a name="declaring-and-passing-classes"></a><span data-ttu-id="d38b3-133">클래스 선언 및 전달</span><span class="sxs-lookup"><span data-stu-id="d38b3-133">Declaring and Passing Classes</span></span>  
 <span data-ttu-id="d38b3-134">클래스에 고정 멤버 레이아웃이 있는 한 관리되지 않은 DLL 함수에 클래스 멤버를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-134">You can pass members of a class to an unmanaged DLL function, as long as the class has a fixed member layout.</span></span> <span data-ttu-id="d38b3-135">다음 예제에서는 `MySystemTime` 클래스의 멤버를 전달하는 방법을 설명합니다. 이 멤버는 User32.dll 파일의 **GetSystemTime**에 순차적으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-135">The following example demonstrates how to pass members of the `MySystemTime` class, which are defined in sequential order, to the **GetSystemTime** in the User32.dll file.</span></span> <span data-ttu-id="d38b3-136">**GetSystemTime**에는 관리되지 않는 다음과 같은 시그니처가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-136">**GetSystemTime** has the following unmanaged signature:</span></span>  
  
```  
void GetSystemTime(SYSTEMTIME* SystemTime);  
```  
  
 <span data-ttu-id="d38b3-137">값 형식과 달리 클래스에는 항상 한 수준의 간접 참조가 하나 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38b3-137">Unlike value types, classes always have at least one level of indirection.</span></span>  
  
```vb  
Imports System  
Imports System.Runtime.InteropServices  
Imports Microsoft.VisualBasic  
  
<StructLayout(LayoutKind.Sequential)> Public Class MySystemTime  
    Public wYear As Short  
    Public wMonth As Short  
    Public wDayOfWeek As Short   
    Public wDay As Short  
    Public wHour As Short  
    Public wMinute As Short  
    Public wSecond As Short  
    Public wMiliseconds As Short  
End Class  
  
Public Class Win32  
    Declare Auto Sub GetSystemTime Lib "Kernel32.dll"(sysTime _  
        As MySystemTime)  
    Declare Auto Function MessageBox Lib "User32.dll"(hWnd As IntPtr, _  
        txt As String, caption As String, Typ As Integer) As Integer  
End Class  
  
Public Class TestPlatformInvoke      
    Public Shared Sub Main()  
        Dim sysTime As New MySystemTime()  
        Win32.GetSystemTime(sysTime)  
  
        Dim dt As String  
        dt = "System time is:" & ControlChars.CrLf & _  
              "Year: " & sysTime.wYear & _  
              ControlChars.CrLf & "Month: " & sysTime.wMonth & _  
              ControlChars.CrLf & "DayOfWeek: " & sysTime.wDayOfWeek & _  
              ControlChars.CrLf & "Day: " & sysTime.wDay  
        Win32.MessageBox(IntPtr.Zero, dt, "Platform Invoke Sample", 0)        
    End Sub  
End Class  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public class MySystemTime {  
    public ushort wYear;   
    public ushort wMonth;  
    public ushort wDayOfWeek;   
    public ushort wDay;   
    public ushort wHour;   
    public ushort wMinute;   
    public ushort wSecond;   
    public ushort wMilliseconds;   
}  
class Win32API {  
    [DllImport("Kernel32.dll")]  
    public static extern void GetSystemTime(MySystemTime st);  
  
    [DllImport("user32.dll", CharSet=CharSet.Auto)]  
     public static extern int MessageBox(IntPtr hWnd,  
         string text, string caption, int options);  
}  
  
public class TestPlatformInvoke  
{  
    public static void Main()  
    {  
        MySystemTime sysTime = new MySystemTime();  
        Win32API.GetSystemTime(sysTime);  
  
        string dt;  
        dt = "System time is: \n" +  
              "Year: " + sysTime.wYear + "\n" +  
              "Month: " + sysTime.wMonth + "\n" +  
              "DayOfWeek: " + sysTime.wDayOfWeek + "\n" +  
              "Day: " + sysTime.wDay;  
        Win32API.MessageBox(IntPtr.Zero, dt, "Platform Invoke Sample", 0);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="d38b3-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d38b3-138">See Also</span></span>  
 [<span data-ttu-id="d38b3-139">DLL 함수 호출</span><span class="sxs-lookup"><span data-stu-id="d38b3-139">Calling a DLL Function</span></span>](../../../docs/framework/interop/calling-a-dll-function.md)  
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>  
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>  
 <xref:System.Runtime.InteropServices.FieldOffsetAttribute>
