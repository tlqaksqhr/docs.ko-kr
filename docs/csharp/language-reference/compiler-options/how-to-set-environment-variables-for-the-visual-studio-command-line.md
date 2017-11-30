---
title: "방법: Visual Studio 명령줄에 필요한 환경 변수 설정"
ms.date: 09-29-2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: cs.build.commandline
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
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8012e310bb04ec3acef0790f9cd50ed42dd9286a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a><span data-ttu-id="6b40b-102">방법: Visual Studio 명령줄에 필요한 환경 변수 설정</span><span class="sxs-lookup"><span data-stu-id="6b40b-102">How to: Set Environment Variables for the Visual Studio Command Line</span></span>

<span data-ttu-id="6b40b-103">VsDevCmd.bat 파일 명령줄 빌드 적절 한 환경 변수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b40b-103">The VsDevCmd.bat file sets the appropriate environment variables to enable command-line builds.</span></span> <span data-ttu-id="6b40b-104">VsDevCmd.bat에 대 한 자세한 내용은 참조 [기술 자료 문서 Q248802](http://go.microsoft.com/fwlink/?LinkId=225042)합니다.</span><span class="sxs-lookup"><span data-stu-id="6b40b-104">For more information about VsDevCmd.bat, see [Knowledge Base article Q248802](http://go.microsoft.com/fwlink/?LinkId=225042).</span></span>  

> [!NOTE]
> <span data-ttu-id="6b40b-105">VsDevCmd.bat 파일은 Visual Studio 2017와 함께 제공 하는 새 파일.</span><span class="sxs-lookup"><span data-stu-id="6b40b-105">The VsDevCmd.bat file is a new file delivered with Visual Studio 2017.</span></span> <span data-ttu-id="6b40b-106">Visual Studio 2015 및 이전 버전에 같은 목적을 위해 VSVARS32.bat를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b40b-106">Visual Studio 2015 and earlier versions used VSVARS32.bat for the same purpose.</span></span> <span data-ttu-id="6b40b-107">이 파일은 \program files\microsoft Visual Studio 저장 된\\*버전*\Common7\Tools or Program Files (x86) \Microsoft Visual Studio\\*버전*\Common7\Tools 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b40b-107">This file was stored in \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools.</span></span>
  
<span data-ttu-id="6b40b-108">또한 Visual Studio의 이전 버전을 보유 하는 컴퓨터에서 현재 버전의 Visual Studio가 설치 되어 VsDevCmd.bat와 VSVARS32 하지 실행 해야 합니다. 동일한 명령 프롬프트 창에서 서로 다른 버전에서 BAT 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b40b-108">If the current version of Visual Studio is installed on a computer that also has an earlier version of Visual Studio, you should not run VsDevCmd.bat and VSVARS32.BAT from different versions in the same Command Prompt window.</span></span> <span data-ttu-id="6b40b-109">대신 별도 창에서 각 버전에 대해 명령을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b40b-109">Instead, you should run the command for each version in its own window.</span></span>
  
### <a name="to-run-vsdevcmdbat"></a><span data-ttu-id="6b40b-110">VsDevCmd.BAT를 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="6b40b-110">To run VsDevCmd.BAT</span></span>  
  
1.  <span data-ttu-id="6b40b-111">**시작** 메뉴를 열고는 **VS 2017 용 개발자 명령 프롬프트**합니다.</span><span class="sxs-lookup"><span data-stu-id="6b40b-111">From the **Start** menu, open the **Developer Command Prompt for VS 2017**.</span></span>  <span data-ttu-id="6b40b-112">에 **Visual Studio 2017** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="6b40b-112">It's in the **Visual Studio 2017** folder.</span></span>
  
2.  <span data-ttu-id="6b40b-113">Files\microsoft Visual Studio로 변경\\*버전*\\*제공*\Common7\Tools or \Program 파일 (x86) \Microsoft Visual Studio\\ *버전*\\*제공*\Common7\Tools 하위 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b40b-113">Change to the \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools or \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools subdirectory of your installation.</span></span>  <span data-ttu-id="6b40b-114">(*버전* 은 *2017* 현재 버전에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b40b-114">(*Version* is *2017* for the current version.</span></span> <span data-ttu-id="6b40b-115">*제공* 중 하나인 *엔터프라이즈*, *Professional* 또는 *커뮤니티*.)</span><span class="sxs-lookup"><span data-stu-id="6b40b-115">*Offering* is one of *Enterprise*, *Professional* or *Community*.)</span></span>
  
3.  <span data-ttu-id="6b40b-116">VsDevCmd.bat 입력 하 여 실행 **VsDevCmd**합니다.</span><span class="sxs-lookup"><span data-stu-id="6b40b-116">Run VsDevCmd.bat by typing **VsDevCmd**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="6b40b-117">VsDevCmd.bat 컴퓨터 마다 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b40b-117">VsDevCmd.bat can vary from computer to computer.</span></span> <span data-ttu-id="6b40b-118">다른 컴퓨터에서 VsDevCmd.bat VsDevCmd.bat 파일이 없거나 손상 된 대체 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b40b-118">Do not replace a missing or damaged VsDevCmd.bat file with a VsDevCmd.bat from another computer.</span></span> <span data-ttu-id="6b40b-119">대신 설치 프로그램을 다시 실행하여 누락된 파일을 교체하십시오.</span><span class="sxs-lookup"><span data-stu-id="6b40b-119">Instead, rerun setup to replace the missing file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b40b-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b40b-120">See Also</span></span>  
 [<span data-ttu-id="6b40b-121">csc.exe를 사용한 명령줄 빌드</span><span class="sxs-lookup"><span data-stu-id="6b40b-121">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
