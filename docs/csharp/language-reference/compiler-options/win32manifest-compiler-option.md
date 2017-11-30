---
title: "-win32manifest(C# 컴파일러 옵션)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /win32manifest
helpviewer_keywords:
- /win32manifest compiler option [C#]
- win32manifest compiler option [C#]
- -win32manifest compiler option [C#]
ms.assetid: 9460ea1b-6c9f-44b8-8f73-301b30a01de1
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 40b1fa1f9aa465a56eccaf5fff5cf7bb59144e85
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="win32manifest-c-compiler-options"></a><span data-ttu-id="f807f-102">/win32manifest(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="f807f-102">/win32manifest (C# Compiler Options)</span></span>
<span data-ttu-id="f807f-103">프로젝트의 PE(포팅 가능한 실행 파일) 파일에 포함할 사용자 정의 Win32 응용 프로그램 매니페스트 파일을 식별하려면 **/win32manifest** 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f807f-103">Use the **/win32manifest** option to specify a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f807f-104">구문</span><span class="sxs-lookup"><span data-stu-id="f807f-104">Syntax</span></span>  
  
```console  
/win32manifest: filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="f807f-105">인수</span><span class="sxs-lookup"><span data-stu-id="f807f-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="f807f-106">사용자 지정 매니페스트 파일의 이름 및 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="f807f-106">The name and location of the custom manifest file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f807f-107">설명</span><span class="sxs-lookup"><span data-stu-id="f807f-107">Remarks</span></span>  
 <span data-ttu-id="f807f-108">기본적으로 [!INCLUDE[csharp_current_short](~/includes/csharp-current-short-md.md)] 컴파일러는 "asInvoker"의 요청된 실행 수준을 지정하는 응용 프로그램 매니페스트를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f807f-108">By default, the [!INCLUDE[csharp_current_short](~/includes/csharp-current-short-md.md)] compiler embeds an application manifest that specifies a requested execution level of "asInvoker."</span></span> <span data-ttu-id="f807f-109">실행 파일이 작성되는 폴더에 매니페스트가 생성됩니다. Visual Studio를 사용하는 경우 대개 bin\Debug 또는 bin\Release 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="f807f-109">It creates the manifest in the same folder in which the executable is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="f807f-110">예를 들어 "highestAvailable" 또는 "requireAdministrator"의 요청된 실행 수준을 지정하기 위해 사용자 지정 매니페스트를 제공하려면 이 옵션을 사용하여 파일 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f807f-110">If you want to supply a custom manifest, for example to specify a requested execution level of "highestAvailable" or "requireAdministrator," use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f807f-111">이 옵션과 [/win32res(C# 컴파일러 옵션)](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f807f-111">This option and the [/win32res (C# Compiler Options)](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) option are mutually exclusive.</span></span> <span data-ttu-id="f807f-112">같은 명령줄에서 두 옵션을 모두 사용하려고 하면 빌드 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f807f-112">If you try to use both options in the same command line you will get a build error.</span></span>  
  
 <span data-ttu-id="f807f-113">매니페스트는 응용 프로그램이 있는 응용 프로그램을 지정 실행 수준을 파일/레지스트리 가상화 Windows 사용자 계정 컨트롤 기능 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f807f-113">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows.</span></span> <span data-ttu-id="f807f-114">자세한 내용은 참조 [사용자 계정 컨트롤](/windows/access-protection/user-account-control/user-account-control-overview)합니다.</span><span class="sxs-lookup"><span data-stu-id="f807f-114">For more information, see [User Account Control](/windows/access-protection/user-account-control/user-account-control-overview).</span></span>  
  
 <span data-ttu-id="f807f-115">다음 조건 중 하나라도 참인 경우 응용 프로그램에 가상화가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f807f-115">Your application will be subject to virtualization if either of these conditions is true:</span></span>  
  
-   <span data-ttu-id="f807f-116">사용자는 **/nowin32manifest** 옵션을 사용하며, **/win32res** 옵션을 사용하여 나중 빌드 단계 또는 Windows Resource(.res) 파일의 일부로 매니페스트를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f807f-116">You use the **/nowin32manifest** option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the **/win32res** option.</span></span>  
  
-   <span data-ttu-id="f807f-117">요청한 실행 수준을 지정하지 않는 사용자 지정 매니페스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f807f-117">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="f807f-118">는 기본 .manifest 파일을 만들고 이를 실행 파일과 함께 debug 및 release 디렉터리에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f807f-118"> creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="f807f-119">텍스트 편집기에서 파일을 만들고 프로젝트에 파일을 추가하여 사용자 지정 매니페스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f807f-119">You can add a custom manifest by creating one in any text editor and then adding the file to the project.</span></span> <span data-ttu-id="f807f-120">또는 **솔루션 탐색기**에서 **프로젝트** 아이콘을 마우스 오른쪽 단추로 클릭하고, **새 항목 추가**와 **응용 프로그램 매니페스트 파일**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f807f-120">Alternatively, you can right-click the **Project** icon in **Solution Explorer**, click **Add New Item**, and then click **Application Manifest File**.</span></span> <span data-ttu-id="f807f-121">신규 또는 기존 매니페스트 파일을 추가하면 **매니페스트** 드롭다운 목록에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f807f-121">After you have added your new or existing manifest file, it will appear in the **Manifest** drop down list.</span></span> <span data-ttu-id="f807f-122">자세한 내용은 [프로젝트 디자이너, 응용 프로그램 페이지(C#)](/visualstudio/ide/reference/application-page-project-designer-csharp)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f807f-122">For more information, see [Application Page, Project Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span></span>  
  
 <span data-ttu-id="f807f-123">[/nowin32manifest(C# 컴파일러 옵션)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md) 옵션을 사용하여 응용 프로그램 매니페스트를 사용자 지정 빌드 후 단계 또는 Win32 리소스 파일의 일부로 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f807f-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the [/nowin32manifest (C# Compiler Options)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md) option.</span></span> <span data-ttu-id="f807f-124">응용 프로그램이 Windows Vista에서 파일 또는 레지스트리 가상화의 적용을 받도록 하려면 동일한 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f807f-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="f807f-125">이렇게 하면 컴파일러가 PE(이식 가능한 실행 파일) 파일에 기본 매니페스트를 만들고 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f807f-125">This will prevent the compiler from creating and embedding a default manifest in the portable executable (PE) file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f807f-126">예제</span><span class="sxs-lookup"><span data-stu-id="f807f-126">Example</span></span>  
 <span data-ttu-id="f807f-127">다음 예제는 Visual C# 컴파일러가 PE에 삽입하는 기본 매니페스트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f807f-127">The following example shows the default manifest that the Visual C# compiler inserts into a PE.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f807f-128">컴파일러는 표준 응용 프로그램 이름인 "MyApplication.app"을 xml에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="f807f-128">The compiler inserts a standard application name " MyApplication.app " into the xml.</span></span> <span data-ttu-id="f807f-129">이는 Windows Server 2003 서비스 팩 3에서 응용 프로그램을 실행하기 위한 해결 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="f807f-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
```xml  
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
  
## <a name="see-also"></a><span data-ttu-id="f807f-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f807f-130">See Also</span></span>  
 [<span data-ttu-id="f807f-131">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="f807f-131">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="f807f-132">/nowin32manifest (C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="f807f-132">/nowin32manifest (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md)  
 [<span data-ttu-id="f807f-133">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="f807f-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
