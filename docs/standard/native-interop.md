---
title: "기본 상호 운용성"
description: ".NET에서 네이티브 구성 요소와 상호 작용하는 방법을 알아봅니다."
keywords: .NET, .NET Core
author: blackdwarf
ms.author: ronpet
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 3c357112-35fb-44ba-a07b-6a1c140370ac
ms.translationtype: HT
ms.sourcegitcommit: 3155295489e1188640dae5aa5bf9fdceb7480ed6
ms.openlocfilehash: 9652986491f087b8fa175e2b4041063c71211178
ms.contentlocale: ko-kr
ms.lasthandoff: 08/21/2017

---

# <a name="native-interoperability"></a><span data-ttu-id="79a42-104">기본 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="79a42-104">Native Interoperability</span></span>

<span data-ttu-id="79a42-105">이 문서에서는 .NET에서 사용할 수 있는 “기본 상호 운용성”을 수행하는 세 가지 방법을 좀 더 자세히 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-105">In this document, we will dive a little bit deeper into all three ways of doing "native interoperability" that are available using .NET.</span></span>

<span data-ttu-id="79a42-106">네이티브 코드를 호출하려는 이유 중 몇 가지는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-106">There are a few of reasons why you would want to call into native code:</span></span>

*   <span data-ttu-id="79a42-107">운영 체제에서 관리되는 클래스 라이브러리에 없는 많은 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-107">Operating Systems come with a large volume of APIs that are not present in the managed class libraries.</span></span> <span data-ttu-id="79a42-108">이러한 경우의 대표적인 예는 하드웨어 또는 운영 체제 관리 기능 액세스입니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-108">A prime example for this would be access to hardware or operating system management functions.</span></span>
*   <span data-ttu-id="79a42-109">C 스타일 ABI(네이티브 ABI)를 포함하거나 생성할 수 있는 다른 구성 요소와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-109">Communicating with other components that have or can produce C-style ABIs (native ABIs).</span></span> <span data-ttu-id="79a42-110">예를 들어 [JNI(Java 기본 인터페이스)](http://docs.oracle.com/javase/8/docs/technotes/guides/jni/)를 통해 표시되는 Java 코드 또는 기본 구성 요소를 생성할 수 있는 다른 모든 관리되는 언어가 여기에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-110">This covers, for example, Java code that is exposed via [Java Native Interface (JNI)](http://docs.oracle.com/javase/8/docs/technotes/guides/jni/) or any other managed language that could produce a native component.</span></span>
*   <span data-ttu-id="79a42-111">Windows에서는 Microsoft Office 제품군 등 설치되는 대부분의 소프트웨어가 해당 프로그램을 나타내며 개발자가 자동화하거나 사용할 수 있도록 하는 COM 구성 요소를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-111">On Windows, most of the software that gets installed, such as Microsoft Office suite, registers COM components that represent their programs and allow developers to automate them or use them.</span></span> <span data-ttu-id="79a42-112">이 경우 기본 상호 운용성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-112">This also requires native interoperability.</span></span>

<span data-ttu-id="79a42-113">물론, 개발자가 기본 구성 요소를 조작하려 하거나 조작해야 하는 모든 잠재적인 상황 및 시나리오가 위 목록에 포함된 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-113">Of course, the list above does not cover all of the potential situations and scenarios in which the developer would want/like/need to interface with native components.</span></span> <span data-ttu-id="79a42-114">예를 들어 .NET 클래스 라이브러리는 기본 상호 운용성 지원을 사용하여 콘솔 지원 및 조작, 파일 시스템 액세스 등의 많은 API를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-114">.NET class library, for instance, uses the native interoperability support to implement a fair number of its APIs, like console support and manipulation, file system access and others.</span></span> <span data-ttu-id="79a42-115">그러나 필요한 경우 한 가지 옵션이 있다는 것에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-115">However, it is important to note that there is an option, should one need it.</span></span>

> [!NOTE]
> <span data-ttu-id="79a42-116">이 문서의 예제는 대부분 .NET Core에 지원되는 세 가지 플랫폼(Windows, Linux 및 macOS)에 대해 모두 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-116">Most of the examples in this document will be presented for all three supported platforms for .NET Core (Windows, Linux and macOS).</span></span> <span data-ttu-id="79a42-117">그러나 간략하고 명확한 일부 예제의 경우 Windows 파일 이름과 확장명(즉, 라이브러리의 경우 “dll”)을 사용하는 한 가지 샘플만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-117">However, for some short and illustrative examples, just one sample is shown that uses Windows filenames and extensions (that is, "dll" for libraries).</span></span> <span data-ttu-id="79a42-118">Linux 또는 macOS에서 해당 기능을 사용할 수 없다는 의미는 아니며, 단지 편의를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-118">This does not mean that those features are not available on Linux or macOS, it was done merely for convenience sake.</span></span>

## <a name="platform-invoke-pinvoke"></a><span data-ttu-id="79a42-119">P/Invoke(플랫폼 호출)</span><span class="sxs-lookup"><span data-stu-id="79a42-119">Platform Invoke (P/Invoke)</span></span>

<span data-ttu-id="79a42-120">P/Invoke는 관리 코드에서 관리되지 않는 라이브러리의 구조체, 콜백 및 함수에 액세스할 수 있는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-120">P/Invoke is a technology that allows you to access structs, callbacks and functions in unmanaged libraries from your managed code.</span></span> <span data-ttu-id="79a42-121">P/Invoke API는 대부분 `System` 및 `System.Runtime.InteropServices`라는 두 네임스페이스에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-121">Most of the P/Invoke API is contained in two namespaces: `System` and `System.Runtime.InteropServices`.</span></span> <span data-ttu-id="79a42-122">이러한 두 네임스페이스를 사용하면 기본 구성 요소와 통신하는 방법을 설명하는 특성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-122">Using these two namespaces will allow you access to the attributes that describe how you want to communicate with the native component.</span></span>

<span data-ttu-id="79a42-123">관리 코드에서 관리되지 않는 함수를 호출하는 가장 일반적인 예제에서 시작하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-123">Let’s start from the most common example, and that is calling unmanaged functions in your managed code.</span></span> <span data-ttu-id="79a42-124">명령줄 응용 프로그램에서 메시지 상자를 표시하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-124">Let’s show a message box from a command-line application:</span></span>

```csharp
using System.Runtime.InteropServices;

public class Program {

    // Import user32.dll (containing the function we need) and define
    // the method corresponding to the native function.
    [DllImport("user32.dll")]
    public static extern int MessageBox(IntPtr hWnd, String text, String caption, int options);

    public static void Main(string[] args) {
        // Invoke the function as a regular managed method.
        MessageBox(IntPtr.Zero, "Command-line message box", "Attention!", 0);
    }
}
```

<span data-ttu-id="79a42-125">위의 예제는 상당히 간단하지만 관리 코드에서 관리되지 않는 함수를 호출하는 데 필요한 사항을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-125">The example above is pretty simple, but it does show off what is needed to invoke unmanaged functions from managed code.</span></span> <span data-ttu-id="79a42-126">예제를 단계별로 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-126">Let’s step through the example:</span></span>

*   <span data-ttu-id="79a42-127">줄 #1에서는 필요한 항목이 모두 포함되어 있는 네임스페이스인 `System.Runtime.InteropServices`에 대한 using 문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-127">Line #1 shows the using statement for the `System.Runtime.InteropServices` which is the namespace that holds all of the items we need.</span></span>
*   <span data-ttu-id="79a42-128">줄 #5에서는 `DllImport` 특성을 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-128">Line #5 introduces the `DllImport` attribute.</span></span> <span data-ttu-id="79a42-129">이 특성은 관리되지 않는 DLL을 로드하도록 런타임에 지정하므로 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-129">This attribute is crucial, as it tells the runtime that it should load the unmanaged DLL.</span></span> <span data-ttu-id="79a42-130">이 DLL을 호출하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-130">This is the DLL into which we wish to invoke.</span></span>
*   <span data-ttu-id="79a42-131">줄 #6은 P/Invoke 작업의 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-131">Line #6 is the crux of the P/Invoke work.</span></span> <span data-ttu-id="79a42-132">관리되지 않는 메서드와 **동일한 시그니처**가 있는 관리되는 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-132">It defines a managed method that has the **exact same signature** as the unmanaged one.</span></span> <span data-ttu-id="79a42-133">선언에서 확인할 수 있는 새 키워드 `extern`은 이 메서드가 외부 메서드이며 호출 시 런타임이 `DllImport` 특성에 지정된 DLL에서 찾도록 런타임에 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-133">The declaration has a new keyword that you can notice, `extern`, which tells the runtime this is an external method, and that when you invoke it, the runtime should find it in the DLL specified in `DllImport` attribute.</span></span>

<span data-ttu-id="79a42-134">예제의 나머지 부분에서는 단순히 다른 관리되는 메서드와 마찬가지로 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-134">The rest of the example is just invoking the method as you would any other managed method.</span></span>

<span data-ttu-id="79a42-135">macOS에 대한 샘플도 이와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-135">The sample is similar for macOS.</span></span> <span data-ttu-id="79a42-136">물론 macOS에서는 다른 동적 라이브러리 명명 체계를 사용하므로 `DllImport` 특성의 라이브러리 이름을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-136">One thing that needs to change is, of course, the name of the library in the `DllImport` attribute, as macOS has a different scheme of naming dynamic libraries.</span></span> <span data-ttu-id="79a42-137">아래 샘플에서는 `getpid(2)` 함수를 사용하여 응용 프로그램의 프로세스 ID를 가져오고 콘솔에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-137">The sample below uses the `getpid(2)` function to get the process ID of the application and print it out to the console.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

        // Import the libc and define the method corresponding to the native function.
        [DllImport("libSystem.dylib")]
        private static extern int getpid();

        public static void Main(string[] args){
            // Invoke the function and get the process ID.
            int pid = getpid();
            Console.WriteLine(pid);
        }
    }
}
```

<span data-ttu-id="79a42-138">물론 Linux에서도 이와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-138">It is similar on Linux, of course.</span></span> <span data-ttu-id="79a42-139">`getpid(2)`는 [POSIX](https://en.wikipedia.org/wiki/POSIX) 시스템 호출이기 때문에 함수 이름이 같습니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-139">The function name is same, since `getpid(2)` is [POSIX](https://en.wikipedia.org/wiki/POSIX) system call.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

        // Import the libc and define the method corresponding to the native function.
        [DllImport("libc.so.6")]
        private static extern int getpid();

        public static void Main(string[] args){
            // Invoke the function and get the process ID.
            int pid = getpid();
            Console.WriteLine(pid);
        }
    }
}
```

### <a name="invoking-managed-code-from-unmanaged-code"></a><span data-ttu-id="79a42-140">비관리 코드에서 관리 코드 호출</span><span class="sxs-lookup"><span data-stu-id="79a42-140">Invoking managed code from unmanaged code</span></span>

<span data-ttu-id="79a42-141">물론, 런타임에서 양방향 통신을 허용하므로 함수 포인터를 사용하여 네이티브 함수에서 관리되는 아티팩트를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-141">Of course, the runtime allows communication to flow both ways which enables you to call into managed artifacts from native functions, using function pointers.</span></span> <span data-ttu-id="79a42-142">관리 코드에서 함수 포인터와 가장 가까운 것은 **대리자**이므로, 대리자를 사용하여 네이티브 코드에서 관리 코드로의 콜백을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-142">The closest thing to a function pointer in managed code is a **delegate**, so this is what is used to allow callbacks from native code into managed code.</span></span>

<span data-ttu-id="79a42-143">이 기능을 사용하는 방법은 위에서 설명한 관리 코드에서 네이티브 코드로의 프로세스와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-143">The way to use this feature is similar to managed to native process described above.</span></span> <span data-ttu-id="79a42-144">지정된 콜백에 대해 시그니처와 일치하는 대리자를 정의하고 외부 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-144">For a given callback, you define a delegate that matches the signature, and pass that into the external method.</span></span> <span data-ttu-id="79a42-145">다른 모든 작업은 런타임에서 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-145">The runtime will take care of everything else.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace ConsoleApplication1 {

    class Program {

        // Define a delegate that corresponds to the unmanaged function.
        delegate bool EnumWC(IntPtr hwnd, IntPtr lParam);

        // Import user32.dll (containing the function we need) and define
        // the method corresponding to the native function.
        [DllImport("user32.dll")]
        static extern int EnumWindows(EnumWC lpEnumFunc, IntPtr lParam);

        // Define the implementation of the delegate; here, we simply output the window handle.
        static bool OutputWindow(IntPtr hwnd, IntPtr lParam) {
            Console.WriteLine(hwnd.ToInt64());
            return true;
        }

        static void Main(string[] args) {
            // Invoke the method; note the delegate as a first parameter.
            EnumWindows(OutputWindow, IntPtr.Zero);
        }
    }
}
```

<span data-ttu-id="79a42-146">예제를 살펴보기 전에 작업해야 하는 관리되지 않는 함수의 시그니처를 확인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-146">Before we walk through our example, it is good to go over the signatures of the unmanaged functions we need to work with.</span></span> <span data-ttu-id="79a42-147">모든 창을 열거하기 위해 호출하려는 함수에는 다음과 같은 시그니처가 있습니다. `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="79a42-147">The function we want to call to enumerate all of the windows has the following signature: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span></span>

<span data-ttu-id="79a42-148">첫 번째 매개 변수는 콜백입니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-148">The first parameter is a callback.</span></span> <span data-ttu-id="79a42-149">이 콜백에는 다음과 같은 시그니처가 있습니다. `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="79a42-149">The said callback has the following signature: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span></span>

<span data-ttu-id="79a42-150">이 점에 유의하여 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-150">With this in mind, let’s walk through the example:</span></span>

*   <span data-ttu-id="79a42-151">예제의 줄 #8에서는 비관리 코드의 콜백 시그니처와 일치하는 대리자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-151">Line #8 in the example defines a delegate that matches the signature of the callback from unmanaged code.</span></span> <span data-ttu-id="79a42-152">관리 코드에서 `IntPtr`을 사용하여 LPARAM 및 HWND 형식을 나타내는 방법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-152">Notice how the LPARAM and HWND types are represented using `IntPtr` in the managed code.</span></span>
*   <span data-ttu-id="79a42-153">줄 #10 및 #11에서는 user32.dll 라이브러리의 `EnumWindows` 함수를 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-153">Lines #10 and #11 introduce the `EnumWindows` function from the user32.dll library.</span></span>
*   <span data-ttu-id="79a42-154">줄 #13-16에서는 대리자를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-154">Lines #13 - 16 implement the delegate.</span></span> <span data-ttu-id="79a42-155">이 간단한 예제에서는 단순히 핸들을 콘솔에 출력하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-155">For this simple example, we just want to output the handle to the console.</span></span>
*   <span data-ttu-id="79a42-156">마지막으로, 줄 #19에서는 외부 메서드를 호출하고 대리자를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-156">Finally, in line #19 we invoke the external method and pass in the delegate.</span></span>

<span data-ttu-id="79a42-157">Linux 및 macOS 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-157">The Linux and macOS examples are shown below.</span></span> <span data-ttu-id="79a42-158">해당 예제에서는 C 라이브러리 `libc`에 있는 `ftw` 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-158">For them, we use the `ftw` function that can be found in `libc`, the C library.</span></span> <span data-ttu-id="79a42-159">이 함수는 디렉터리 계층 구조를 트래버스하는 데 사용되며, 함수에 대한 포인터를 해당 매개 변수 중 하나로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-159">This function is used to traverse directory hierarchies and it takes a pointer to a function as one of its parameters.</span></span> <span data-ttu-id="79a42-160">이 함수에는 다음과 같은 시그니처가 있습니다. `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.</span><span class="sxs-lookup"><span data-stu-id="79a42-160">The said function has the following signature: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

            // Define a delegate that has the same signature as the native function.
            delegate int DirClbk(string fName, StatClass stat, int typeFlag);

            // Import the libc and define the method to represent the native function.
            [DllImport("libc.so.6")]
            static extern int ftw(string dirpath, DirClbk cl, int descriptors);

            // Implement the above DirClbk delegate;
            // this one just prints out the filename that is passed to it.
            static int DisplayEntry(string fName, StatClass stat, int typeFlag) {
                    Console.WriteLine(fName);
                    return 0;
            }

            public static void Main(string[] args){
                    // Call the native function.
                    // Note the second parameter which represents the delegate (callback).
                    ftw(".", DisplayEntry, 10);
            }
    }

    // The native callback takes a pointer to a struct. The below class
    // represents that struct in managed code. You can find more information
    // about this in the section on marshalling below.
    [StructLayout(LayoutKind.Sequential)]
    public class StatClass {
            public uint DeviceID;
            public uint InodeNumber;
            public uint Mode;
            public uint HardLinks;
            public uint UserID;
            public uint GroupID;
            public uint SpecialDeviceID;
            public ulong Size;
            public ulong BlockSize;
            public uint Blocks;
            public long TimeLastAccess;
            public long TimeLastModification;
            public long TimeLastStatusChange;
    }
}
```

<span data-ttu-id="79a42-161">macOS 예제에서는 동일한 함수를 사용하며, macOS에서 `libc`가 다른 위치에 유지되므로 `DllImport` 특성에 대한 인수만 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-161">macOS example uses the same function, and the only difference is the argument to the `DllImport` attribute, as macOS keeps `libc` in a different place.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
        public static class Program {

                // Define a delegate that has the same signature as the native function.
                delegate int DirClbk(string fName, StatClass stat, int typeFlag);

                // Import the libc and define the method to represent the native function.
                [DllImport("libSystem.dylib")]
                static extern int ftw(string dirpath, DirClbk cl, int descriptors);

                // Implement the above DirClbk delegate;
                // this one just prints out the filename that is passed to it.
                static int DisplayEntry(string fName, StatClass stat, int typeFlag) {
                        Console.WriteLine(fName);
                        return 0;
                }

                public static void Main(string[] args){
                        // Call the native function.
                        // Note the second parameter which represents the delegate (callback).
                        ftw(".", DisplayEntry, 10);
                }
        }

        // The native callback takes a pointer to a struct. The below class
        // represents that struct in managed code. You can find more information
        // about this in the section on marshalling below.
        [StructLayout(LayoutKind.Sequential)]
        public class StatClass {
                public uint DeviceID;
                public uint InodeNumber;
                public uint Mode;
                public uint HardLinks;
                public uint UserID;
                public uint GroupID;
                public uint SpecialDeviceID;
                public ulong Size;
                public ulong BlockSize;
                public uint Blocks;
                public long TimeLastAccess;
                public long TimeLastModification;
                public long TimeLastStatusChange;
        }
}
```

<span data-ttu-id="79a42-162">위의 두 예제에서는 매개 변수를 사용하며, 두 경우 모두 매개 변수가 관리되는 형식으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-162">Both of the above examples depend on parameters, and in both cases, the parameters are given as managed types.</span></span> <span data-ttu-id="79a42-163">런타임에서 “올바른 작업”을 수행하고 다른 쪽의 해당 항목으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-163">Runtime does the "right thing" and processes these into its equivalents on the other side.</span></span> <span data-ttu-id="79a42-164">이 프로세스는 고품질 네이티브 interop 코드를 작성하는 데 매우 중요하므로 런타임에서 형식을 _마샬링_하면 어떻게 되는지를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-164">Since this process is really important to writing quality native interop code, let’s take a look at what happens when the runtime _marshals_ the types.</span></span>

## <a name="type-marshalling"></a><span data-ttu-id="79a42-165">형식 마샬링</span><span class="sxs-lookup"><span data-stu-id="79a42-165">Type marshalling</span></span>

<span data-ttu-id="79a42-166">**마샬링**은 관리되는 경계를 넘어 네이티브로 변환되거나 그 반대로 변환되어야 할 때 형식을 변환하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-166">**Marshalling** is the process of transforming types when they need to cross the managed boundary into native and vice versa.</span></span>

<span data-ttu-id="79a42-167">마샬링이 필요한 이유는 관리 코드와 비관리 코드의 형식이 서로 다르기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-167">The reason marshalling is needed is because the types in the managed and unmanaged code are different.</span></span> <span data-ttu-id="79a42-168">예를 들어 관리 코드에서는 `String`을 사용하지만 관리되지 않는 환경에서는 문자열이 유니코드(“와이드”), 비유니코드, null 종료, ASCII 등일 수 있습니다. 기본적으로 P/Invoke 하위 시스템은 [MSDN](https://msdn.microsoft.com/library/zah6xy75.aspx)에서 확인할 수 있는 기본 동작에 따라 올바른 작업을 수행하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-168">In managed code, for instance, you have a `String`, while in the unmanaged world strings can be Unicode ("wide"), non-Unicode, null-terminated, ASCII, etc. By default, the P/Invoke subsystem will try to do the Right Thing based on the default behavior which you can see on [MSDN](https://msdn.microsoft.com/library/zah6xy75.aspx).</span></span> <span data-ttu-id="79a42-169">그러나 추가 제어가 필요한 경우 `MarshalAs` 특성을 사용하여 관리되지 않는 쪽에서 필요한 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-169">However, for those situations where you need extra control, you can employ the `MarshalAs` attribute to specify what is the expected type on the unmanaged side.</span></span> <span data-ttu-id="79a42-170">예를 들어 문자열을 null 종료 ANSI 문자열로 보내려는 경우 다음과 같이 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-170">For instance, if we want the string to be sent as a null-terminated ANSI string, we could do it like this:</span></span>

```csharp
[DllImport("somenativelibrary.dll")]
static extern int MethodA([MarshalAs(UnmanagedType.LPStr)] string parameter);
```

### <a name="marshalling-classes-and-structs"></a><span data-ttu-id="79a42-171">클래스 및 구조체 마샬링</span><span class="sxs-lookup"><span data-stu-id="79a42-171">Marshalling classes and structs</span></span>

<span data-ttu-id="79a42-172">형식 마샬링의 또 다른 측면은 관리되지 않는 메서드에 구조체를 전달하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-172">Another aspect of type marshalling is how to pass in a struct to an unmanaged method.</span></span> <span data-ttu-id="79a42-173">예를 들어 관리되지 않는 일부 메서드의 경우 매개 변수로 구조체가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-173">For instance, some of the unmanaged methods require a struct as a parameter.</span></span> <span data-ttu-id="79a42-174">이러한 경우 관리되는 부분에서 해당 구조체 또는 클래스를 만들어 매개 변수로 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-174">In these cases, we need to create a corresponding struct or a class in managed part of the world to use it as a parameter.</span></span> <span data-ttu-id="79a42-175">그러나 클래스 정의만으로는 충분하지 않습니다. 클래스의 필드를 관리되지 않는 구조체에 매핑하는 방법도 마샬러에 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-175">However, just defining the class is not enough, we also need to instruct the marshaler how to map fields in the class to the unmanaged struct.</span></span> <span data-ttu-id="79a42-176">이때 `StructLayout` 특성이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-176">This is where the `StructLayout` attribute comes into play.</span></span>

```csharp
[DllImport("kernel32.dll")]
static extern void GetSystemTime(SystemTime systemTime);

[StructLayout(LayoutKind.Sequential)]
class SystemTime {
    public ushort Year;
    public ushort Month;
    public ushort DayOfWeek;
    public ushort Day;
    public ushort Hour;
    public ushort Minute;
    public ushort Second;
    public ushort Milsecond;
}

public static void Main(string[] args) {
    SystemTime st = new SystemTime();
    GetSystemTime(st);
    Console.WriteLine(st.Year);
}
```

<span data-ttu-id="79a42-177">위의 예제에서는 `GetSystemTime()` 함수를 호출하는 간단한 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-177">The example above shows off a simple example of calling into `GetSystemTime()` function.</span></span> <span data-ttu-id="79a42-178">흥미로운 부분은 줄 4에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-178">The interesting bit is on line 4.</span></span> <span data-ttu-id="79a42-179">특성이 클래스의 필드를 다른 쪽(비관리)의 구조체에 순차적으로 매핑하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-179">The attribute specifies that the fields of the class should be mapped sequentially to the struct on the other (unmanaged) side.</span></span> <span data-ttu-id="79a42-180">즉, 아래와 같이 관리되지 않는 구조체에 대응해야 하므로 필드의 이름 지정은 중요하지 않고 해당 순서만 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-180">This means that the naming of the fields is not important, only their order is important, as it needs to correspond to the unmanaged struct, shown below:</span></span>

```c
typedef struct _SYSTEMTIME {
  WORD wYear;
  WORD wMonth;
  WORD wDayOfWeek;
  WORD wDay;
  WORD wHour;
  WORD wMinute;
  WORD wSecond;
  WORD wMilliseconds;
} SYSTEMTIME, *PSYSTEMTIME*;
```

<span data-ttu-id="79a42-181">이전 예제에서 이와 관련된 Linux 및 macOS 예제를 이미 살펴봤습니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-181">We already saw the Linux and macOS example for this in the previous example.</span></span> <span data-ttu-id="79a42-182">해당 예제가 아래에 다시 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-182">It is shown again below.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential)]
public class StatClass {
        public uint DeviceID;
        public uint InodeNumber;
        public uint Mode;
        public uint HardLinks;
        public uint UserID;
        public uint GroupID;
        public uint SpecialDeviceID;
        public ulong Size;
        public ulong BlockSize;
        public uint Blocks;
        public long TimeLastAccess;
        public long TimeLastModification;
        public long TimeLastStatusChange;
}
```

<span data-ttu-id="79a42-183">`StatClass` 클래스는 UNIX 시스템의 `stat` 시스템 호출에서 반환되는 구조체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-183">The `StatClass` class represents a structure that is returned by the `stat` system call on UNIX systems.</span></span> <span data-ttu-id="79a42-184">지정된 파일에 대한 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-184">It represents information about a given file.</span></span> <span data-ttu-id="79a42-185">위의 클래스는 관리 코드의 stat 구조체 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-185">The class above is the stat struct representation in managed code.</span></span> <span data-ttu-id="79a42-186">앞서 말했듯이, 클래스의 필드는 네이티브 구조체와 동일한 순서여야 하며(선택한 UNIX 구현에 대한 기본 페이지에서 확인할 수 있음), 동일한 기본 형식을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-186">Again, the fields in the class have to be in the same order as the native struct (you can find these by perusing man pages on your favorite UNIX implementation) and they have to be of the same underlying type.</span></span>

## <a name="more-resources"></a><span data-ttu-id="79a42-187">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="79a42-187">More resources</span></span>

*   <span data-ttu-id="79a42-188">[PInvoke.net wiki](http://www.pinvoke.net)는 일반적인 Win32 API 및 호출 방법에 대한 정보가 포함된 우수한 Wiki입니다.</span><span class="sxs-lookup"><span data-stu-id="79a42-188">[PInvoke.net wiki](http://www.pinvoke.net) an excellent Wiki with information on common Win32 APIs and how to call them.</span></span>
*   [<span data-ttu-id="79a42-189">MSDN의 P/Invoke</span><span class="sxs-lookup"><span data-stu-id="79a42-189">P/Invoke on MSDN</span></span>](https://msdn.microsoft.com/library/zbz07712.aspx)
*   [<span data-ttu-id="79a42-190">P/Invoke에 대한 Mono 설명서</span><span class="sxs-lookup"><span data-stu-id="79a42-190">Mono documentation on P/Invoke</span></span>](http://www.mono-project.com/docs/advanced/pinvoke/)

