---
title: "/win32manifest (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4a9693bd7eb03dee5a2a9f2d43360b963e9fd876
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="win32manifest-visual-basic"></a><span data-ttu-id="36963-102">/win32manifest(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36963-102">/win32manifest (Visual Basic)</span></span>
<span data-ttu-id="36963-103">프로젝트의 PE(포팅 가능한 실행 파일) 파일에 포함할 사용자 정의 Win32 응용 프로그램 매니페스트 파일을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="36963-103">Identifies a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36963-104">구문</span><span class="sxs-lookup"><span data-stu-id="36963-104">Syntax</span></span>  
  
```  
/win32manifest: fileName  
```  
  
## <a name="arguments"></a><span data-ttu-id="36963-105">인수</span><span class="sxs-lookup"><span data-stu-id="36963-105">Arguments</span></span>  
  
|<span data-ttu-id="36963-106">용어</span><span class="sxs-lookup"><span data-stu-id="36963-106">Term</span></span>|<span data-ttu-id="36963-107">정의</span><span class="sxs-lookup"><span data-stu-id="36963-107">Definition</span></span>|  
|---|---|  
|`fileName`|<span data-ttu-id="36963-108">사용자 지정 매니페스트 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="36963-108">The path of the custom manifest file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36963-109">주의</span><span class="sxs-lookup"><span data-stu-id="36963-109">Remarks</span></span>  
 <span data-ttu-id="36963-110">기본적으로 Visual Basic 컴파일러는 asInvoker의 요청 된 실행 수준을 지정 하는 응용 프로그램 매니페스트를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="36963-110">By default, the Visual Basic compiler embeds an application manifest that specifies a requested execution level of asInvoker.</span></span> <span data-ttu-id="36963-111">실행 파일이 작성 되는, 일반적으로 bin\Debug 또는 bin\Release 폴더 Visual Studio를 사용 하는 경우 동일한 폴더에 매니페스트가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36963-111">It creates the manifest in the same folder in which the executable file is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="36963-112">예를 들어 requireAdministrator 또는 highestAvailable의 요청 된 실행 수준을 지정 하려면 사용자 지정 매니페스트를 제공 하려는 경우 파일의 이름을 지정 하려면이 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="36963-112">If you want to supply a custom manifest, for example to specify a requested execution level of highestAvailable or requireAdministrator, use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36963-113">이 옵션 및 [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36963-113">This option and the [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) option are mutually exclusive.</span></span> <span data-ttu-id="36963-114">동일한 명령줄에서 두 옵션을 사용 하려고 하면 빌드 오류가 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36963-114">If you try to use both options in the same command line, you will get a build error.</span></span>  
  
 <span data-ttu-id="36963-115">매니페스트는 응용 프로그램이 있는 응용 프로그램을 Windows Vista의 사용자 계정 컨트롤 기능 파일/레지스트리 가상화는 요청 된 실행 수준이 됩니다 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36963-115">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows Vista.</span></span> <span data-ttu-id="36963-116">가상화에 대 한 자세한 내용은 참조 [Windows Vista의 ClickOnce 배포](https://docs.microsoft.com/visualstudio/deployment/clickonce-deployment-on-windows-vista)합니다.</span><span class="sxs-lookup"><span data-stu-id="36963-116">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](https://docs.microsoft.com/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="36963-117">다음 조건 중 하나에 해당 하는 경우에 응용 프로그램 가상화가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36963-117">Your application will be subject to virtualization if either of the following conditions is true:</span></span>  
  
1.  <span data-ttu-id="36963-118">사용 된 `/nowin32manifest` 옵션을 할 수 없으며 Windows 리소스 (.res) 파일의 일부 또는 이후 빌드 단계에서 매니페스트를 사용 하 여는 `/win32resource` 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="36963-118">You use the `/nowin32manifest` option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the `/win32resource` option.</span></span>  
  
2.  <span data-ttu-id="36963-119">요청된 된 실행 수준을 지정 하지 않는 사용자 지정 매니페스트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="36963-119">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]<span data-ttu-id="36963-120">기본.manifest 파일을 만들고 실행 파일과 함께 디버그 및 릴리스 디렉터리에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="36963-120"> creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="36963-121">보거나 클릭 하 여 기본 app.manifest 파일을 편집할 수 있습니다 **UAC 설정 보기** 에 **응용 프로그램** 프로젝트 디자이너 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="36963-121">You can view or edit the default app.manifest file by clicking **View UAC Settings** on the **Application** tab in the Project Designer.</span></span> <span data-ttu-id="36963-122">자세한 내용은 참조 [응용 프로그램 페이지, 프로젝트 디자이너 (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="36963-122">For more information, see [Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="36963-123">사용자 지정 빌드 후 단계 또는 Win32 리소스 파일의 일부로 사용 하 여 응용 프로그램 매니페스트를 제공할 수는 `/nowin32manifest` 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="36963-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the `/nowin32manifest` option.</span></span> <span data-ttu-id="36963-124">응용 프로그램을 Windows Vista에서 파일 또는 레지스트리 가상화 하려는 경우 동일한 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="36963-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="36963-125">이렇게 하면 컴파일러에서 만들고 기본 매니페스트는 PE 파일에 포함 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="36963-125">This will prevent the compiler from creating and embedding a default manifest in the PE file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36963-126">예제</span><span class="sxs-lookup"><span data-stu-id="36963-126">Example</span></span>  
 <span data-ttu-id="36963-127">다음 예제에서는 Visual Basic 컴파일러는 PE 삽입 기본 매니페스트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="36963-127">The following example shows the default manifest that the Visual Basic compiler inserts into a PE.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36963-128">컴파일러는 XML 매니페스트에 표준 응용 프로그램 이름 MyApplication.app를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="36963-128">The compiler inserts a standard application name MyApplication.app into the manifest XML.</span></span> <span data-ttu-id="36963-129">Windows Server 2003 서비스 팩 3에서 실행할 응용 프로그램을 사용 하도록 설정 하는 해결 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="36963-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <assemblyIdentity version="1.0.0.0" name="MyApplication.app"/>  
  <trustInfo xmlns="urn:schemas-microsoft-com:asm.v2">  
    <security>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <requestedExecutionLevel level="asInvoker"/>  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
</assembly>  
```  
  
## <a name="see-also"></a><span data-ttu-id="36963-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36963-130">See Also</span></span>  
 <span data-ttu-id="36963-131">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="36963-131">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="36963-132"> [/nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)</span><span class="sxs-lookup"><span data-stu-id="36963-132"> [/nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)</span></span>
