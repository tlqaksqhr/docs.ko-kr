---
title: '방법: Visual Studio 명령줄에 필요한 환경 변수 설정'
ms.date: 09/29/2017
f1_keywords:
- cs.build.commandline
helpviewer_keywords:
- csc.exe, command-line builds
- Visual C#, command-line builds
- command-line compilers, Visual C#
- Vsvars32.bat
- builds [C#], command-line
- compilers, invoking from command line
- Vcvars32.bat file
- command line [C#], building from
- Visual C# compiler, enabling
- compiling source code, from command line
ms.assetid: 7ec09480-5612-4f6a-8d00-ad90ea9bca5d
ms.openlocfilehash: 0935cb62244691af7fa450fef9c1ab8f6c616579
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33214993"
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a><span data-ttu-id="08b52-102">방법: Visual Studio 명령줄에 필요한 환경 변수 설정</span><span class="sxs-lookup"><span data-stu-id="08b52-102">How to: Set Environment Variables for the Visual Studio Command Line</span></span>

<span data-ttu-id="08b52-103">VsDevCmd.bat 파일은 명령줄 빌드를 사용하도록 적절한 환경 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="08b52-103">The VsDevCmd.bat file sets the appropriate environment variables to enable command-line builds.</span></span> <span data-ttu-id="08b52-104">VsDevCmd.bat에 대한 자세한 내용은 [기술 자료 문서 Q248802](https://support.microsoft.com/help/248802/you-receive-the-out-of-environment-space-error-message-when-you-execut)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08b52-104">For more information about VsDevCmd.bat, see [Knowledge Base article Q248802](https://support.microsoft.com/help/248802/you-receive-the-out-of-environment-space-error-message-when-you-execut).</span></span>  

> [!NOTE]
> <span data-ttu-id="08b52-105">VsDevCmd.bat 파일은 Visual Studio 2017과 함께 제공되는 새로운 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="08b52-105">The VsDevCmd.bat file is a new file delivered with Visual Studio 2017.</span></span> <span data-ttu-id="08b52-106">Visual Studio 2015 및 이전 버전에서도 VSVARS32.bat가 같은 용도로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b52-106">Visual Studio 2015 and earlier versions used VSVARS32.bat for the same purpose.</span></span> <span data-ttu-id="08b52-107">이 파일은 \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools 또는 Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools에 저장되었습니다.</span><span class="sxs-lookup"><span data-stu-id="08b52-107">This file was stored in \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools.</span></span>
  
<span data-ttu-id="08b52-108">Visual Studio의 이전 버전이 설치된 컴퓨터에 Visual Studio의 최신 버전을 설치한 경우 동일한 명령 프롬프트 창에서 다른 버전의 VsDevCmd.bat 또는 VSVARS32.BAT를 실행해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08b52-108">If the current version of Visual Studio is installed on a computer that also has an earlier version of Visual Studio, you should not run VsDevCmd.bat and VSVARS32.BAT from different versions in the same Command Prompt window.</span></span> <span data-ttu-id="08b52-109">대신 별도 창에서 각 버전에 대해 명령을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08b52-109">Instead, you should run the command for each version in its own window.</span></span>
  
### <a name="to-run-vsdevcmdbat"></a><span data-ttu-id="08b52-110">VsDevCmd.BAT를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="08b52-110">To run VsDevCmd.BAT</span></span>  
  
1.  <span data-ttu-id="08b52-111">**시작** 메뉴에서 **VS 2017용 개발자 명령 프롬프트**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="08b52-111">From the **Start** menu, open the **Developer Command Prompt for VS 2017**.</span></span>  <span data-ttu-id="08b52-112">**Visual Studio 2017** 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b52-112">It's in the **Visual Studio 2017** folder.</span></span>
  
2.  <span data-ttu-id="08b52-113">설치 경로를 \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools or \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools 하위 디렉터리로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="08b52-113">Change to the \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools or \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools subdirectory of your installation.</span></span>  <span data-ttu-id="08b52-114">(*Version*은 현재 버전용인 *2017*입니다.</span><span class="sxs-lookup"><span data-stu-id="08b52-114">(*Version* is *2017* for the current version.</span></span> <span data-ttu-id="08b52-115">*Offering*은 *Enterprise*, *Professional* 또는 *Community* 중 하나입니다.)</span><span class="sxs-lookup"><span data-stu-id="08b52-115">*Offering* is one of *Enterprise*, *Professional* or *Community*.)</span></span>
  
3.  <span data-ttu-id="08b52-116">**VsDevCmd**를 입력하여 VsDevCmd.bat을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="08b52-116">Run VsDevCmd.bat by typing **VsDevCmd**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="08b52-117">VsDevCmd.bat는 컴퓨터마다 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b52-117">VsDevCmd.bat can vary from computer to computer.</span></span> <span data-ttu-id="08b52-118">누락되거나 손상된 VsDevCmd.bat 파일을 다른 컴퓨터의 VsDevCmd.bat 파일로 바꾸지 마세요.</span><span class="sxs-lookup"><span data-stu-id="08b52-118">Do not replace a missing or damaged VsDevCmd.bat file with a VsDevCmd.bat from another computer.</span></span> <span data-ttu-id="08b52-119">대신 설치 프로그램을 다시 실행하여 누락된 파일을 교체하십시오.</span><span class="sxs-lookup"><span data-stu-id="08b52-119">Instead, rerun setup to replace the missing file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08b52-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08b52-120">See Also</span></span>  
 [<span data-ttu-id="08b52-121">csc.exe를 사용한 명령줄 빌드</span><span class="sxs-lookup"><span data-stu-id="08b52-121">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
