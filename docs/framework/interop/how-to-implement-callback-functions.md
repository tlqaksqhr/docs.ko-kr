---
title: '방법: 콜백 함수 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- callback function, implementing
ms.assetid: e55b3712-b9ea-4453-bd9a-ad5cfa2f6bfa
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e081347129ce367cf6b46ca29c07a016bb64ab95
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-implement-callback-functions"></a><span data-ttu-id="25fe1-102">방법: 콜백 함수 구현</span><span class="sxs-lookup"><span data-stu-id="25fe1-102">How to: Implement Callback Functions</span></span>
<span data-ttu-id="25fe1-103">다음 절차 및 예제에서는 관리되는 응용 프로그램이 플랫폼 호출을 사용하여 로컬 컴퓨터에서 각 창에 대한 핸들 값을 인쇄하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25fe1-103">The following procedure and example demonstrate how a managed application, using platform invoke, can print the handle value for each window on the local computer.</span></span> <span data-ttu-id="25fe1-104">특히 프로시저 및 예제에서는 **EnumWindows** 함수를 사용하여 창 목록을 단계별로 실행하고 관리되는 콜백 함수(CallBack)를 사용하여 창 핸들 값을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="25fe1-104">Specifically, the procedure and example use the **EnumWindows** function to step through the list of windows and a managed callback function (named CallBack) to print the value of the window handle.</span></span>  
  
### <a name="to-implement-a-callback-function"></a><span data-ttu-id="25fe1-105">콜백 함수를 구현하려면</span><span class="sxs-lookup"><span data-stu-id="25fe1-105">To implement a callback function</span></span>  
  
1.  <span data-ttu-id="25fe1-106">구현을 계속 진행하기 전에 **EnumWindows** 함수에 대한 시그니처를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="25fe1-106">Look at the signature for the **EnumWindows** function before going further with the implementation.</span></span> <span data-ttu-id="25fe1-107">**EnumWindows**에는 다음 시그니처가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25fe1-107">**EnumWindows** has the following signature:</span></span>  
  
    ```  
    BOOL EnumWindows(WNDENUMPROC lpEnumFunc, LPARAM lParam)  
    ```  
  
     <span data-ttu-id="25fe1-108">이 함수에 콜백이 필요한 한 가지 단서는 **lpEnumFunc** 인수가 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="25fe1-108">One clue that this function requires a callback is the presence of the **lpEnumFunc** argument.</span></span> <span data-ttu-id="25fe1-109">일반적으로 포인터를 콜백 함수로 이동하는 인수의 이름에서 **Func** 접미사와 결합된 **lp**(long pointer) 접두사를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="25fe1-109">It is common to see the **lp** (long pointer) prefix combined with the **Func** suffix in the name of arguments that take a pointer to a callback function.</span></span> <span data-ttu-id="25fe1-110">Win32 함수에 대한 설명서는 Microsoft Platform SDK를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="25fe1-110">For documentation about Win32 functions, see the Microsoft Platform SDK.</span></span>  
  
2.  <span data-ttu-id="25fe1-111">관리되는 콜백 함수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="25fe1-111">Create the managed callback function.</span></span> <span data-ttu-id="25fe1-112">예제에서는 두 인수(**hwnd** 및 **lparam**)를 사용하는 `CallBack`이라는 대리자 형식을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="25fe1-112">The example declares a delegate type, called `CallBack`, which takes two arguments (**hwnd** and **lparam**).</span></span> <span data-ttu-id="25fe1-113">첫 번째 인수는 창에 대한 핸들이고 두 번째 인수는 응용 프로그램에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="25fe1-113">The first argument is a handle to the window; the second argument is application-defined.</span></span> <span data-ttu-id="25fe1-114">이 릴리스에서 두 인수는 모두 정수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25fe1-114">In this release, both arguments must be integers.</span></span>  
  
     <span data-ttu-id="25fe1-115">일반적으로 콜백 함수는 성공을 나타내는 0이 아닌 값 및 실패를 나타내는 0을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="25fe1-115">Callback functions generally return nonzero values to indicate success and zero to indicate failure.</span></span> <span data-ttu-id="25fe1-116">이 예제에서는 반환 값을 **true**로 명시적으로 설정하여 열거를 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="25fe1-116">This example explicitly sets the return value to **true** to continue the enumeration.</span></span>  
  
3.  <span data-ttu-id="25fe1-117">대리자를 만들고 **EnumWindows** 함수에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="25fe1-117">Create a delegate and pass it as an argument to the **EnumWindows** function.</span></span> <span data-ttu-id="25fe1-118">플랫폼 호출은 대리자를 친숙한 콜백 형식으로 자동으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="25fe1-118">Platform invoke converts the delegate to a familiar callback format automatically.</span></span>  
  
4.  <span data-ttu-id="25fe1-119">콜백 함수가 작업을 완료하기 전에 가비지 수집기가 대리자를 회수하지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="25fe1-119">Ensure that the garbage collector does not reclaim the delegate before the callback function completes its work.</span></span> <span data-ttu-id="25fe1-120">대리자를 매개 변수로 전달하거나 구조체에 필드로 포함된 대리자를 전달하면 호출 중에 대리자가 수집되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25fe1-120">When you pass a delegate as a parameter, or pass a delegate contained as a field in a structure, it remains uncollected for the duration of the call.</span></span> <span data-ttu-id="25fe1-121">따라서 다음 열거 예제처럼 콜백 함수는 호출이 반환되기 전에 작업을 완료하고 관리되는 호출자의 추가적인 작업이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25fe1-121">So, as is the case in the following enumeration example, the callback function completes its work before the call returns and requires no additional action by the managed caller.</span></span>  
  
     <span data-ttu-id="25fe1-122">그러나 호출이 반환된 후에 콜백 함수를 호출할 수 있으면 관리되는 호출자는 단계에 따라 콜백 함수가 완료될 때까지 대리자가 수집되지 않는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25fe1-122">If, however, the callback function can be invoked after the call returns, the managed caller must take steps to ensure that the delegate remains uncollected until the callback function finishes.</span></span> <span data-ttu-id="25fe1-123">가비지 수집을 방지하는 방법에 대한 자세한 내용은 플랫폼 호출을 사용한 [Interop 마샬링](../../../docs/framework/interop/interop-marshaling.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="25fe1-123">For detailed information about preventing garbage collection, see [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md) with Platform Invoke.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25fe1-124">예</span><span class="sxs-lookup"><span data-stu-id="25fe1-124">Example</span></span>  
  
```vb  
Imports System  
Imports System.Runtime.InteropServices  
  
Public Delegate Function CallBack( _  
hwnd As Integer, lParam As Integer) As Boolean  
  
Public Class EnumReportApp  
  
    Declare Function EnumWindows Lib "user32" ( _  
       x As CallBack, y As Integer) As Integer  
  
    Public Shared Sub Main()  
        EnumWindows(AddressOf EnumReportApp.Report, 0)  
    End Sub 'Main  
  
    Public Shared Function Report(hwnd As Integer, lParam As Integer) _  
    As Boolean  
        Console.Write("Window handle is ")  
        Console.WriteLine(hwnd)  
        Return True  
    End Function 'Report  
End Class 'EnumReportApp  
```  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
  
public delegate bool CallBack(int hwnd, int lParam);  
  
public class EnumReportApp  
{  
    [DllImport("user32")]  
    public static extern int EnumWindows(CallBack x, int y);   
  
    public static void Main()   
    {  
        CallBack myCallBack = new CallBack(EnumReportApp.Report);  
        EnumWindows(myCallBack, 0);  
    }  
  
    public static bool Report(int hwnd, int lParam)  
    {   
        Console.Write("Window handle is ");  
        Console.WriteLine(hwnd);  
        return true;  
    }  
}  
```  
  
```cpp  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
// A delegate type.  
delegate bool CallBack(int hwnd, int lParam);  
  
// Managed type with the method to call.  
ref class EnumReport  
{  
// Report the window handle.  
public:  
    [DllImport("user32")]  
    static int EnumWindows(CallBack^ x, int y);  
  
    static void Main()  
    {  
        EnumReport^ er = gcnew EnumReport;  
        CallBack^ myCallBack = gcnew CallBack(&EnumReport::Report);  
        EnumWindows(myCallBack, 0);  
    }  
  
    static bool Report(int hwnd, int lParam)  
    {  
       Console::Write(L"Window handle is ");  
       Console::WriteLine(hwnd);  
       return true;  
    }  
};  
  
int main()  
{  
    EnumReport::Main();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="25fe1-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25fe1-125">See Also</span></span>  
 [<span data-ttu-id="25fe1-126">콜백 함수</span><span class="sxs-lookup"><span data-stu-id="25fe1-126">Callback Functions</span></span>](../../../docs/framework/interop/callback-functions.md)  
 [<span data-ttu-id="25fe1-127">DLL 함수 호출</span><span class="sxs-lookup"><span data-stu-id="25fe1-127">Calling a DLL Function</span></span>](../../../docs/framework/interop/calling-a-dll-function.md)
