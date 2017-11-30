---
title: "방법: 플랫폼 호출을 사용하여 웨이브 파일 재생(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
caps.latest.revision: "30"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d037e17ef48ebfdd5cfd860efbacf195e7b6a76d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-platform-invoke-to-play-a-wave-file-c-programming-guide"></a><span data-ttu-id="32d16-102">방법: 플랫폼 호출을 사용하여 웨이브 파일 재생(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="32d16-102">How to: Use Platform Invoke to Play a Wave File (C# Programming Guide)</span></span>
<span data-ttu-id="32d16-103">다음 C# 코드 예제에서는 플랫폼 호출 서비스를 사용하여 Windows 운영 체제에서 .wav 사운드 파일을 재생하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="32d16-103">The following C# code example illustrates how to use platform invoke services to play a wave sound file on the Windows operating system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32d16-104">예제</span><span class="sxs-lookup"><span data-stu-id="32d16-104">Example</span></span>  
 <span data-ttu-id="32d16-105">이 예제 코드에서는 `DllImport`를 사용하여 `winmm.dll`의 `PlaySound` 메서드 진입점을 `Form1 PlaySound()`로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="32d16-105">This example code uses `DllImport` to import `winmm.dll`'s `PlaySound` method entry point as `Form1 PlaySound()`.</span></span> <span data-ttu-id="32d16-106">이 예제에는 단추를 포함하는 간단한 Windows Form이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32d16-106">The example has a simple Windows Form with a button.</span></span> <span data-ttu-id="32d16-107">단추를 클릭하면 재생할 파일을 열 수 있도록 표준 Windows <xref:System.Windows.Forms.OpenFileDialog> 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="32d16-107">Clicking the button opens a standard windows <xref:System.Windows.Forms.OpenFileDialog> dialog box so that you can open a file to play.</span></span> <span data-ttu-id="32d16-108">웨이브 파일을 선택하면 winmm.DLL 어셈블리 메서드의 `PlaySound()` 메서드를 사용하여 재생됩니다.</span><span class="sxs-lookup"><span data-stu-id="32d16-108">When a wave file is selected, it is played by using the `PlaySound()` method of the winmm.DLL assembly method.</span></span> <span data-ttu-id="32d16-109">winmm.dll의 `PlaySound` 메서드에 대한 자세한 내용은 [파형 오디오 파일과 함께 PlaySound 함수 사용](http://go.microsoft.com/fwlink/?LinkId=148553)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32d16-109">For more information about winmm.dll's `PlaySound` method, see [Using the PlaySound function with Waveform-Audio Files](http://go.microsoft.com/fwlink/?LinkId=148553).</span></span> <span data-ttu-id="32d16-110">.wav 확장명을 가진 파일을 찾아서 선택한 다음 **열기**를 클릭하여 플랫폼 호출을 통해 웨이브 파일을 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="32d16-110">Browse and select a file that has a .wav extension, and then click **Open** to play the wave file by using platform invoke.</span></span> <span data-ttu-id="32d16-111">텍스트 상자에 선택한 파일의 전체 경로가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="32d16-111">A text box shows the full path of the file selected.</span></span>  
  
 <span data-ttu-id="32d16-112">**파일 열기** 대화 상자가 필터 설정을 통해 .wav 확장명을 가진 파일만 표시하도록 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="32d16-112">The **Open Files** dialog box is filtered to show only files that have a .wav extension through the filter settings:</span></span>  
  
 [!code-csharp[csProgGuideInterop#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_1.cs)]  
  
 [!code-csharp[csProgGuideInterop#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_2.cs)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="32d16-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="32d16-113">Compiling the Code</span></span>  
  
### <a name="to-compile-the-code"></a><span data-ttu-id="32d16-114">코드를 컴파일하려면</span><span class="sxs-lookup"><span data-stu-id="32d16-114">To compile the code</span></span>  
  
1.  <span data-ttu-id="32d16-115">Visual Studio에서 새 C# Windows 응용 프로그램 프로젝트를 만들고 이름을 **WinSound**로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="32d16-115">Create a new C# Windows Application project in Visual Studio and name it **WinSound**.</span></span>  
  
2.  <span data-ttu-id="32d16-116">위의 코드를 복사하여 `Form1.cs` 파일 내용 위에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="32d16-116">Copy the code above, and paste it over the contents of the `Form1.cs` file.</span></span>  
  
3.  <span data-ttu-id="32d16-117">다음 코드를 복사하여 `Form1.Designer.cs` 파일의 `InitializeComponent()` 메서드에서 기존 코드 뒤에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="32d16-117">Copy the following code, and paste it in the `Form1.Designer.cs` file, in the `InitializeComponent()` method, after any existing code.</span></span>  
  
     [!code-csharp[csProgGuideInterop#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_3.cs)]  
  
4.  <span data-ttu-id="32d16-118">코드를 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="32d16-118">Compile and run the code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="32d16-119">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="32d16-119">.NET Framework Security</span></span>  
 <span data-ttu-id="32d16-120">자세한 내용은 [.NET Framework 보안](http://go.microsoft.com/fwlink/?LinkId=37122)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32d16-120">For more information, see [.NET Framework Security](http://go.microsoft.com/fwlink/?LinkId=37122).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32d16-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32d16-121">See Also</span></span>  
 [<span data-ttu-id="32d16-122">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="32d16-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="32d16-123">상호 운용성 개요</span><span class="sxs-lookup"><span data-stu-id="32d16-123">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 [<span data-ttu-id="32d16-124">상호 운용성 개요</span><span class="sxs-lookup"><span data-stu-id="32d16-124">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 [<span data-ttu-id="32d16-125">좀 더 자세히 살펴보고 플랫폼 호출</span><span class="sxs-lookup"><span data-stu-id="32d16-125">A Closer Look at Platform Invoke</span></span>](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
 [<span data-ttu-id="32d16-126">플랫폼 호출을 사용하여 데이터 마샬링</span><span class="sxs-lookup"><span data-stu-id="32d16-126">Marshaling Data with Platform Invoke</span></span>](../../../framework/interop/marshaling-data-with-platform-invoke.md)
