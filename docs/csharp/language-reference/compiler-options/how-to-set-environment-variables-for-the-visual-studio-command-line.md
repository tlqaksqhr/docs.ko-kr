---
title: "방법: Visual Studio 명령줄에 필요한 환경 변수 설정"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.build.commandline
dev_langs:
- CSharp
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
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 569683169c6d7ae50c33ed06d3b365a663f16715
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a><span data-ttu-id="31cfd-102">방법: Visual Studio 명령줄에 필요한 환경 변수 설정</span><span class="sxs-lookup"><span data-stu-id="31cfd-102">How to: Set Environment Variables for the Visual Studio Command Line</span></span>
<span data-ttu-id="31cfd-103">vsvars32.bat 파일은 명령줄 빌드를 사용하도록 적절한 환경 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="31cfd-103">The vsvars32.bat file sets the appropriate environment variables to enable command-line builds.</span></span> <span data-ttu-id="31cfd-104">vsvars32.bat에 대한 자세한 내용은 [기술 자료 문서 Q248802](http://go.microsoft.com/fwlink/?LinkId=225042)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31cfd-104">For more information about vsvars32.bat, see [Knowledge Base article Q248802](http://go.microsoft.com/fwlink/?LinkId=225042).</span></span>  
  
 <span data-ttu-id="31cfd-105">Visual Studio의 이전 버전이 설치된 컴퓨터에 Visual Studio의 최신 버전을 설치한 경우 동일한 명령 프롬프트 창에서 다른 버전의 vsvars32.bat 또는 vcvars32.bat를 실행해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31cfd-105">If the current version of Visual Studio is installed on a computer that also has an earlier version of Visual Studio, you should not run vsvars32.bat or vcvars32.bat from different versions in the same Command Prompt window.</span></span>  
  
### <a name="to-run-vsvars32bat"></a><span data-ttu-id="31cfd-106">VSVARS32.BAT를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="31cfd-106">To run VSVARS32.BAT</span></span>  
  
1.  <span data-ttu-id="31cfd-107">**시작** 메뉴에서 **VS2012용 개발자 명령 프롬프트**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="31cfd-107">From the **Start** menu, open the **Developer Command Prompt for VS2012**.</span></span>  
  
2.  <span data-ttu-id="31cfd-108">경로를 설치되어 있는 Visual Studio의 Program Files\Microsoft Visual Studio *Version*\Common7\Tools 또는 Program Files (x86)\Microsoft Visual Studio *Version*\Common7\Tools 하위 디렉터리로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="31cfd-108">Change to the Program Files\Microsoft Visual Studio *Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio *Version*\Common7\Tools subdirectory of your installation.</span></span>  
  
3.  <span data-ttu-id="31cfd-109">**VSVARS32**를 입력하여 VSVARS32.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="31cfd-109">Run VSVARS32.bat by typing **VSVARS32**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="31cfd-110">VSVARS32.bat는 컴퓨터마다 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31cfd-110">VSVARS32.bat can vary from computer to computer.</span></span> <span data-ttu-id="31cfd-111">누락되거나 손상된 VSVARS32.bat 파일을 다른 컴퓨터의 VSVARS32.bat 파일로 바꾸지 마세요.</span><span class="sxs-lookup"><span data-stu-id="31cfd-111">Do not replace a missing or damaged VSVARS32.bat file with a VSVARS32.bat from another computer.</span></span> <span data-ttu-id="31cfd-112">대신 설치 프로그램을 다시 실행하여 누락된 파일을 교체하십시오.</span><span class="sxs-lookup"><span data-stu-id="31cfd-112">Instead, rerun setup to replace the missing file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31cfd-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31cfd-113">See Also</span></span>  
 [<span data-ttu-id="31cfd-114">csc.exe를 사용한 명령줄 빌드</span><span class="sxs-lookup"><span data-stu-id="31cfd-114">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)

