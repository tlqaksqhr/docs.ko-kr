---
title: Fuslogvw.exe(어셈블리 바인딩 로그 뷰어)
ms.date: 03/30/2017
helpviewer_keywords:
- failed assembly binds
- Fuslogvw.exe
- displaying failed assembly bind details
- assemblies [.NET Framework], failed assembly binds
- locating assemblies
- Assembly Binding Log Viewer
ms.assetid: e32fa443-0778-4cc3-bf36-5c8ea297d296
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73fa08f92a4572a501be65f05e8141c349cc003e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="fuslogvwexe-assembly-binding-log-viewer"></a><span data-ttu-id="a4cb3-102">Fuslogvw.exe(어셈블리 바인딩 로그 뷰어)</span><span class="sxs-lookup"><span data-stu-id="a4cb3-102">Fuslogvw.exe (Assembly Binding Log Viewer)</span></span>
<span data-ttu-id="a4cb3-103">어셈블리 바인딩 로그 뷰어는 어셈블리 바인딩에 대한 자세한 내용을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-103">The Assembly Binding Log Viewer displays details for assembly binds.</span></span> <span data-ttu-id="a4cb3-104">이 정보를 검토하면 .NET Framework에서 런타임에 어셈블리를 찾지 못하는 이유를 진단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-104">This information helps you diagnose why the .NET Framework cannot locate an assembly at run time.</span></span> <span data-ttu-id="a4cb3-105">이러한 오류는 일반적으로 어셈블리가 잘못된 위치에 배포되었거나 네이티브 이미지가 더 이상 유효하지 않거나 버전 번호 또는 문화권이 일치하지 않기 때문에 일어납니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-105">These failures are usually the result of an assembly deployed to the wrong location, a native image that is no longer valid, or a mismatch in version numbers or cultures.</span></span> <span data-ttu-id="a4cb3-106">공용 언어 런타임의 어셈블리 찾기 오류는 일반적으로 응용 프로그램에서 <xref:System.TypeLoadException>으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-106">The common language runtime's failure to locate an assembly typically shows up as a <xref:System.TypeLoadException> in your application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a4cb3-107">Fuslogvw.exe는 관리자 권한으로 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-107">You must run fuslogvw.exe with administrator privileges.</span></span>  
  
 <span data-ttu-id="a4cb3-108">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-108">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="a4cb3-109">이 도구를 실행하려면 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 관리자 자격 증명과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-109">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7) with administrator credentials.</span></span> <span data-ttu-id="a4cb3-110">자세한 내용은 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-110">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="a4cb3-111">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-111">At the command prompt, type the following:</span></span>  
  
```  
fuslogvw  
```  
  
 <span data-ttu-id="a4cb3-112">뷰어에서는 실패한 각 어셈블리 바인딩의 엔트리를 표시하고</span><span class="sxs-lookup"><span data-stu-id="a4cb3-112">The viewer displays an entry for each failed assembly bind.</span></span> <span data-ttu-id="a4cb3-113">실패한 각각의 경우에 대해 바인딩을 시작한 응용 프로그램, 바인딩 대상 어셈블리(이름, 버전, 문화권, 공개 키 포함) 및 오류가 발생한 날짜와 시간 등에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-113">For each failure, the viewer describes the application that initiated the bind; the assembly the bind is for, including name, version, culture and public key; and the date and time of the failure.</span></span>  
  
### <a name="to-change-the-log-location-view"></a><span data-ttu-id="a4cb3-114">로그 위치 보기를 변경하려면</span><span class="sxs-lookup"><span data-stu-id="a4cb3-114">To change the log location view</span></span>  
  
1.  <span data-ttu-id="a4cb3-115">**기본값** 옵션 단추를 선택하여 모든 응용 프로그램 종류에 대한 바인딩 실패를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-115">Select the **Default** option button to view bind failures for all application types.</span></span> <span data-ttu-id="a4cb3-116">기본적으로 로그 항목은 디스크의 사용자별 디렉터리에서 wininet 캐시에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-116">By default, log entries are stored in per-user directories on disk in the wininet cache.</span></span>  
  
2.  <span data-ttu-id="a4cb3-117">**사용자 지정** 옵션 단추를 선택하여 사용자 지정 디렉터리의 바인딩 오류를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-117">Select the **Custom** option button to view bind failures in a custom directory that you specify.</span></span> <span data-ttu-id="a4cb3-118">유효한 디렉터리 이름을 위해 **로그 설정** 대화 상자에서 사용자 지정 로그 위치를 설정하여 런타임에 로그를 저장할 사용자 지정 위치를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-118">You must specify the custom location where you want the runtime to store the logs by setting the custom log location in the **Log Settings** dialog to a valid directory name.</span></span> <span data-ttu-id="a4cb3-119">이 디렉터리는 런타임에 생성되는 파일만 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-119">This directory should be clean, and only contain files that the runtime generates.</span></span> <span data-ttu-id="a4cb3-120">실패하여 로그를 남길 수 있는 실행 파일이 들어 있으면 도구에서 실행 파일과 같은 이름으로 디렉터리를 만들려고 시도하므로 실패한 경우 로그를 남길 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-120">If it contains an executable that generates a failure to be logged, the failure will not be logged because the tool tries to create a directory with the same name as the executable.</span></span> <span data-ttu-id="a4cb3-121">또한 로그 위치에서 실행 파일을 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-121">In addition, an attempt to run an executable from the log location will fail.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a4cb3-122">사용자 지정 바인딩 위치보다 기본 바인딩 위치를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-122">The default bind location is preferable to the custom bind location.</span></span> <span data-ttu-id="a4cb3-123">런타임은 기본 바인딩 위치를 wininet 캐시에 저장하기 때문에 자동으로 이 위치를 비웁니다. 그러나 사용자 지정 바인딩 위치를 지정하는 경우에는 사용자가 직접 비워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-123">The runtime stores the default bind location in the wininet cache, and therefore automatically cleans it out. If you specify a custom bind location, you are responsible for cleaning it out.</span></span>  
  
### <a name="to-view-details-about-a-specific-failure"></a><span data-ttu-id="a4cb3-124">특정 오류에 대한 자세한 내용을 보려면</span><span class="sxs-lookup"><span data-stu-id="a4cb3-124">To view details about a specific failure</span></span>  
  
1.  <span data-ttu-id="a4cb3-125">뷰어에서 원하는 엔트리의 응용 프로그램 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-125">Select the application name of the desired entry in the viewer.</span></span>  
  
2.  <span data-ttu-id="a4cb3-126">**로그 보기** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-126">Click the **View Log** button.</span></span> <span data-ttu-id="a4cb3-127">또는 선택한 엔트리를 두 번 클릭할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-127">Alternately, you can double-click the selected entry.</span></span>  
  
     <span data-ttu-id="a4cb3-128">다음과 같이 선택한 바인딩 오류에 대한 자세한 내용이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-128">The tool displays the following details about the selected bind failure:</span></span>  
  
    -   <span data-ttu-id="a4cb3-129">"파일을 찾을 수 없습니다." 또는 "버전이 일치하지 않습니다." 등 바인딩이 실패한 특정 원인</span><span class="sxs-lookup"><span data-stu-id="a4cb3-129">The specific reason the bind failed, such as "file not found" or "version mismatch".</span></span>  
  
    -   <span data-ttu-id="a4cb3-130">이름, 응용 프로그램의 루트 디렉터리(AppBase) 및 개인 검색 경로(있는 경우)의 설명 등을 포함하여 바인딩을 시작한 응용 프로그램에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="a4cb3-130">Information about the application that initiated the bind, including its name, the application's root directory (AppBase), and a description of the private search path, if there is one.</span></span>  
  
    -   <span data-ttu-id="a4cb3-131">도구에서 찾고 있는 어셈블리의 ID</span><span class="sxs-lookup"><span data-stu-id="a4cb3-131">The identity of the assembly the tool is looking for.</span></span>  
  
    -   <span data-ttu-id="a4cb3-132">적용된 응용 프로그램, 게시자 또는 관리자 버전 정책 설명</span><span class="sxs-lookup"><span data-stu-id="a4cb3-132">A description of any Application, Publisher, or Administrator version policies that have been applied.</span></span>  
  
    -   <span data-ttu-id="a4cb3-133">[전역 어셈블리 캐시](../../../docs/framework/app-domains/gac.md)에 어셈블리가 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="a4cb3-133">Whether the assembly was found in the [global assembly cache](../../../docs/framework/app-domains/gac.md).</span></span>  
  
    -   <span data-ttu-id="a4cb3-134">검색하는 모든 URL 목록</span><span class="sxs-lookup"><span data-stu-id="a4cb3-134">A list of all probing URLs.</span></span>  
  
 <span data-ttu-id="a4cb3-135">다음 샘플 로그 엔트리는 실패한 어셈블리 바인딩에 대한 자세한 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-135">The following sample log entry shows detailed information about a failed assembly bind.</span></span>  
  
```  
*** Assembly Binder Log Entry  (3/5/2007 @ 12:54:20 PM) ***  
  
The operation failed.  
Bind result: hr = 0x80070002. The system cannot find the file specified.  
  
Assembly manager loaded from:  C:\WINNT\Microsoft.NET\Framework\v2.0.50727\fusion.dll  
Running under executable  C:\Program Files\Microsoft.NET\FrameworkSDK\Samples\Tutorials\resourcesandlocalization\graphic\cs\graphicfailtest.exe  
--- A detailed error log follows.   
  
=== Pre-bind state information ===  
LOG: DisplayName = graphicfailtest.resources, Version=0.0.0.0, Culture=en-US, PublicKeyToken=null  
 (Fully-specified)  
LOG: Appbase = C:\Program Files\Microsoft.NET\FrameworkSDK\Samples\Tutorials\resourcesandlocalization\graphic\cs\  
LOG: Initial PrivatePath = NULL  
LOG: Dynamic Base = NULL  
LOG: Cache Base = NULL  
LOG: AppName = NULL  
Calling assembly : graphicfailtest, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.  
===  
  
LOG: Processing DEVPATH.  
LOG: DEVPATH is not set. Falling through to regular bind.  
LOG: Policy not being applied to reference at this time (private, custom, partial, or location-based assembly bind).  
LOG: Post-policy reference: graphicfailtest.resources, Version=0.0.0.0, Culture=en-US, PublicKeyToken=null  
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources.DLL.  
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources/graphicfailtest.resources.DLL.  
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources.EXE.  
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources/graphicfailtest.resources.EXE.  
LOG: All probing URLs attempted and failed.  
```  
  
### <a name="to-delete-a-single-entry-from-the-log"></a><span data-ttu-id="a4cb3-136">로그에서 단일 엔트리를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="a4cb3-136">To delete a single entry from the log</span></span>  
  
1.  <span data-ttu-id="a4cb3-137">뷰어에서 엔트리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-137">Select an entry in the viewer.</span></span>  
  
2.  <span data-ttu-id="a4cb3-138">**항목 삭제** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-138">Click the **Delete Entry** button.</span></span>  
  
### <a name="to-delete-all-entries-from-the-log"></a><span data-ttu-id="a4cb3-139">로그에서 모든 엔트리를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="a4cb3-139">To delete all entries from the log</span></span>  
  
-   <span data-ttu-id="a4cb3-140">**모두 삭제** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-140">Click the **Delete All** button.</span></span>  
  
### <a name="to-refresh-the-user-interface"></a><span data-ttu-id="a4cb3-141">사용자 인터페이스를 새로 고치려면</span><span class="sxs-lookup"><span data-stu-id="a4cb3-141">To refresh the user interface</span></span>  
  
-   <span data-ttu-id="a4cb3-142">**새로 고침** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-142">Click the **Refresh** button.</span></span> <span data-ttu-id="a4cb3-143">뷰어는 실행 중인 동안에는 새 로그 엔트리를 자동으로 검색하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-143">The viewer does not automatically detect new log entries while it is running.</span></span> <span data-ttu-id="a4cb3-144">새 항목을 표시하려면 **새로 고침** 단추를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-144">You must use the **Refresh** button to display them.</span></span>  
  
### <a name="to-change-the-log-settings"></a><span data-ttu-id="a4cb3-145">로그 설정을 변경하려면</span><span class="sxs-lookup"><span data-stu-id="a4cb3-145">To change the log settings</span></span>  
  
-   <span data-ttu-id="a4cb3-146">**설정** 단추를 클릭하여 **로그 설정** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-146">Click the **Settings** button to open the **Log Settings** dialog.</span></span>  
  
### <a name="to-view-the-about-dialog"></a><span data-ttu-id="a4cb3-147">정보 상자를 보려면</span><span class="sxs-lookup"><span data-stu-id="a4cb3-147">To view the About dialog</span></span>  
  
-   <span data-ttu-id="a4cb3-148">**정보** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-148">Click the **About** button.</span></span>  
  
## <a name="binding-logs-for-native-images"></a><span data-ttu-id="a4cb3-149">네이티브 이미지에 대한 바인딩 로그</span><span class="sxs-lookup"><span data-stu-id="a4cb3-149">Binding Logs for Native Images</span></span>  
 <span data-ttu-id="a4cb3-150">기본적으로 Fuslogvw.exe는 일반 어셈블리 바인딩 요청을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-150">By default, Fuslogvw.exe logs normal assembly bind requests.</span></span> <span data-ttu-id="a4cb3-151">또는 [Ngen.exe(네이티브 이미지 생성기)](../../../docs/framework/tools/ngen-exe-native-image-generator.md)를 사용하여 생성된 네이티브 이미지에 대한 어셈블리 바인딩을 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-151">Alternatively, you can log assembly binds for native images that were created using the [Ngen.exe (Native Image Generator)](../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>  
  
#### <a name="to-log-assembly-binds-for-native-images"></a><span data-ttu-id="a4cb3-152">네이티브 이미지에 대한 어셈블리 바인딩을 기록하려면</span><span class="sxs-lookup"><span data-stu-id="a4cb3-152">To log assembly binds for native images</span></span>  
  
-   <span data-ttu-id="a4cb3-153">**로그 범주** 그룹에서 **네이티브 이미지** 옵션 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-153">In the **Log Categories** group, select the **Native Images** option button.</span></span>  
  
 <span data-ttu-id="a4cb3-154">다음 로그에서는 응용 프로그램에 대한 네이티브 이미지가 생성되었을 때 종속성이 존재하지 않아 발생한 실패를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-154">The following log shows a failure caused by a dependency that did not exist when the native image was created for the application.</span></span> <span data-ttu-id="a4cb3-155">런타임에서의 종속성과 Ngen.exe가 실행될 때의 종속성이 다른 경우 네이티브 이미지에 대한 바인딩을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-155">If the dependencies at run time differ from the dependencies when Ngen.exe is run, binding to a native image is not allowed.</span></span>  
  
```  
*** Assembly Binder Log Entry  (12/8/2006 @ 5:22:07 PM) ***  
  
The operation failed.  
Bind result: hr = 0x80070002. The system cannot find the file specified.  
  
Assembly manager loaded from:  E:\Windows\Microsoft.NET\Framework64\v2.0.50727\mscorwks.dll  
Running under executable  E:\test\App.exe  
--- A detailed error log follows.   
  
LOG: Start binding of native image App, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.  
LOG: IL assembly loaded from E:\test\App.exe.  
LOG: Start validating native image App, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.  
LOG: Start validating all the dependencies.  
LOG: [Level 1]Start validating native image dependency mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089.  
LOG: Dependency evaluation succeeded.  
LOG: [Level 1]Start validating IL dependency b, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.  
WRN: Dependency assembly was not found at ngen time, but is found at binding time. Disallow using this native image.  
WRN: No matching native image found.  
LOG: Bind to native image assembly did not succeed. Use IL image.  
```  
  
 <span data-ttu-id="a4cb3-156">다음 로그에서는 응용 프로그램이 실행되었을 때의 컴퓨터 보안 설정이 네이티브 이미지가 생성되었을 때의 보안 설정과 달라 발생하는 네이티브 이미지 바인딩 실패를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-156">The following log shows a native image binding failure that occurred because the security settings on the computer when the application was run were different from the security settings at the time the native image was created.</span></span>  
  
```  
*** Assembly Binder Log Entry  (12/8/2006 @ 5:29:09 PM) ***  
  
The operation failed.  
Bind result: hr = 0x80004005. Unspecified error  
  
Assembly manager loaded from:  E:\Windows\Microsoft.NET\Framework64\v2.0.50727\mscorwks.dll  
Running under executable  E:\test\Application101622.exe  
--- A detailed error log follows.   
  
LOG: Start binding of native image Application101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.  
LOG: IL assembly loaded from E:\test\Application101622.exe.  
LOG: Start validating native image Application101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.  
LOG: Start validating all the dependencies.  
LOG: [Level 1]Start validating native image dependency mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089.  
LOG: Dependency evaluation succeeded.  
LOG: [Level 1]Start validating IL dependency Dependency101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.  
LOG: Dependency evaluation succeeded.  
LOG: Validation of dependencies succeeded.  
LOG: Start loading all the dependencies into load context.  
LOG: Loading of dependencies succeeded.  
LOG: Bind to native image succeeded.  
Native image has correct version information.  
Attempting to use native image E:\Windows\assembly\NativeImages_v2.0.50727_64\Application101622\1ac7fadabec4f72575d807501e9fdc72\Application101622.ni.exe.  
Rejecting native image because it failed the security check. The assembly's permissions must have changed since the time it was ngenned, or it is running with a different security context.  
Discarding native image.  
```  
  
## <a name="the-log-settings-dialog"></a><span data-ttu-id="a4cb3-157">로그 설정 대화 상자</span><span class="sxs-lookup"><span data-stu-id="a4cb3-157">The Log Settings Dialog</span></span>  
 <span data-ttu-id="a4cb3-158">**로그 설정** 대화 상자를 사용하여 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-158">You can use the **Log Settings** dialog to perform the following actions.</span></span>  
  
#### <a name="to-disable-logging"></a><span data-ttu-id="a4cb3-159">로깅을 사용하지 않으려면</span><span class="sxs-lookup"><span data-stu-id="a4cb3-159">To disable logging</span></span>  
  
-   <span data-ttu-id="a4cb3-160">**로그 사용 안 함** 옵션 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-160">Select the **Log disabled** option button.</span></span>  <span data-ttu-id="a4cb3-161">이 옵션은 기본적으로 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-161">Note that this option is selected by default.</span></span>  
  
#### <a name="to-log-assembly-binds-in-exceptions"></a><span data-ttu-id="a4cb3-162">예외에 어셈블리 바인딩을 기록하려면</span><span class="sxs-lookup"><span data-stu-id="a4cb3-162">To log assembly binds in exceptions</span></span>  
  
-   <span data-ttu-id="a4cb3-163">**예외 텍스트로 기록** 옵션 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-163">Select the **Log in exception text** option button.</span></span> <span data-ttu-id="a4cb3-164">덜 자세한 fusion 로그 정보만 예외 텍스트로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-164">Only the least detailed fusion log information is logged in exception text.</span></span> <span data-ttu-id="a4cb3-165">전체 정보를 보려면 다른 설정 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-165">To view full information, use one of the other settings.</span></span>  
  
     <span data-ttu-id="a4cb3-166">도메인 중립적으로 로드되는 어셈블리에 대한 중요 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-166">See the Important note regarding assemblies that are loaded as domain neutral.</span></span>  
  
#### <a name="to-log-assembly-bind-failures"></a><span data-ttu-id="a4cb3-167">어셈블리 바인딩 실패를 기록하려면</span><span class="sxs-lookup"><span data-stu-id="a4cb3-167">To log assembly bind failures</span></span>  
  
-   <span data-ttu-id="a4cb3-168">**디스크에 바인드 실패 기록** 옵션 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-168">Select the **Log bind failures to disk** option button.</span></span>  
  
     <span data-ttu-id="a4cb3-169">도메인 중립적으로 로드되는 어셈블리에 대한 중요 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-169">See the Important note regarding assemblies that are loaded as domain neutral.</span></span>  
  
#### <a name="to-log-all-assembly-binds"></a><span data-ttu-id="a4cb3-170">모든 어셈블리 바인딩을 기록하려면</span><span class="sxs-lookup"><span data-stu-id="a4cb3-170">To log all assembly binds</span></span>  
  
-   <span data-ttu-id="a4cb3-171">**디스크에 모든 바인드 기록** 옵션 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-171">Select the **Log all binds to disk** option button.</span></span>  
  
     <span data-ttu-id="a4cb3-172">도메인 중립적으로 로드되는 어셈블리에 대한 중요 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-172">See the Important note regarding assemblies that are loaded as domain neutral.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a4cb3-173">예를 들어 <xref:System.AppDomainSetup.LoaderOptimization%2A> 속성을 <xref:System.LoaderOptimization.MultiDomain?displayProperty=nameWithType> 또는 <xref:System.LoaderOptimization.MultiDomainHost?displayProperty=nameWithType>로 설정하여 어셈블리가 도메인 중립적으로 로드되는 경우 로깅을 설정하면 경우에 따라 메모리가 누수될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-173">When an assembly is loaded as domain neutral, for example by setting the <xref:System.AppDomainSetup.LoaderOptimization%2A> property to <xref:System.LoaderOptimization.MultiDomain?displayProperty=nameWithType> or <xref:System.LoaderOptimization.MultiDomainHost?displayProperty=nameWithType>, turning on logging might leak memory in some cases.</span></span> <span data-ttu-id="a4cb3-174">도메인 중립 모듈이 응용 프로그램 도메인에 로드되었을 때 로그 엔트리가 만들어지고 나중에 응용 프로그램 도메인이 언로드되면 이러한 누수가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-174">This can happen if a log entry is made when a domain-neutral module is loaded into an application domain, and later the application domain is unloaded.</span></span> <span data-ttu-id="a4cb3-175">프로세스가 끝날 때까지는 로그 엔트리가 해제되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-175">The log entry might not be released until the process ends.</span></span> <span data-ttu-id="a4cb3-176">로깅이 자동으로 설정되는 디버거도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-176">Some debuggers automatically turn on logging.</span></span>  
  
#### <a name="to-enable-a-custom-log-path"></a><span data-ttu-id="a4cb3-177">사용자 지정 로그 경로를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="a4cb3-177">To enable a custom log path</span></span>  
  
1.  <span data-ttu-id="a4cb3-178">**사용자 지정 로그 경로 사용** 옵션 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-178">Select the **Enable custom log path** option button.</span></span>  
  
2.  <span data-ttu-id="a4cb3-179">**사용자 지정 로그 경로** 텍스트 상자에 경로를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-179">Enter the path into the **Custom log path** text box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4cb3-180">[어셈블리 바인딩 로그 뷰어(Fuslogvw.exe)](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md)에서는 IE(Internet Explorer) 캐시를 사용하여 바인딩 로그를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-180">The [Assembly Binding Log Viewer (Fuslogvw.exe)](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md) uses the Internet Explorer (IE) cache to store its binding log.</span></span> <span data-ttu-id="a4cb3-181">가끔 나타나는 IE 캐시 손상으로 인해 [어셈블리 바인딩 로그 뷰어(Fuslogvw.exe)](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md)에서는 보기 창에 새 바인딩 로그를 표시하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-181">Due to occasional corruption in the IE cache, the [Assembly Binding Log Viewer (Fuslogvw.exe)](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md) can sometimes stop showing new binding logs in the viewing window.</span></span> <span data-ttu-id="a4cb3-182">이 손상으로 인해 .NET 바인딩 인프라(fusion)는 바인딩 로그에 쓰거나 바인딩 로그에서 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-182">As a result of this corruption, the .NET binding infrastructure (fusion) cannot write to or read from the binding log.</span></span> <span data-ttu-id="a4cb3-183">사용자 지정 로그 경로를 사용하는 경우에는 이 문제가 발생하지 않습니다.  손상을 해결하고 fusion이 바인딩 로그를 다시 표시하도록 하려면 IE 옵션 대화 상자 내에서 임시 인터넷 파일을 삭제하여 IE 캐시를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-183">(This issue is not encountered if you use a custom log path.)  To fix the corruption and allow fusion to show binding logs again, clear the IE cache by deleting temporary internet files from within the IE Internet Options dialog.</span></span>  
>   
>  <span data-ttu-id="a4cb3-184">관리되지 않는 응용 프로그램에서 `IHostAssemblyManager` 및 `IHostAssemblyStore` 인터페이스를 구현하여 공용 언어 런타임을 호스팅하는 경우 로그 엔트리를 wininet 캐시에 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-184">If your unmanaged application hosts the common language runtime by implementing the `IHostAssemblyManager` and `IHostAssemblyStore` interfaces, log entries can't be stored in the wininet cache.</span></span>  <span data-ttu-id="a4cb3-185">이러한 인터페이스를 구현하는 사용자 지정 호스트에 대한 로그 엔트리를 보려면 대체 로그 경로를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-185">To view log entries for custom hosts that implement these interfaces, you must specify an alternate log path.</span></span>  
  
#### <a name="to-enable-logging-for-apps-running-in-the-windows-app-container"></a><span data-ttu-id="a4cb3-186">Windows 앱 컨테이너에서 실행되는 앱에 대해 로깅을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="a4cb3-186">To enable logging for apps running in the Windows app container</span></span>  
  
1.  <span data-ttu-id="a4cb3-187">이전 절차에서 설명한 대로, 사용자 지정 로그 경로를 활성화시킵니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-187">Enable a custom log path, as described in the previous procedure.</span></span> <span data-ttu-id="a4cb3-188">기본적으로, Windows 앱 컨테이너에서 실행되는 응용 프로그램은 하드 디스크에 대한 액세스가 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-188">By default, apps that are running in the Windows app container have limited access to the hard disk.</span></span> <span data-ttu-id="a4cb3-189">지정한 디렉터리는 응용 프로그램 컨테이너에 있는 모든 응용 프로그램에 대한 읽기/쓰기 권한을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-189">The directory you specify will have read/write access for all apps in the app container.</span></span>  
  
2.  <span data-ttu-id="a4cb3-190">**로깅 몰입 활성화** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-190">Select the **Enable immersive logging** check box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a4cb3-191">Windows 8 이상에서만 상자가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4cb3-191">This box is enabled only on Windows 8 or later.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4cb3-192">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4cb3-192">See Also</span></span>  
 <xref:System.TypeLoadException>  
 [<span data-ttu-id="a4cb3-193">도구</span><span class="sxs-lookup"><span data-stu-id="a4cb3-193">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="a4cb3-194">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="a4cb3-194">Global Assembly Cache</span></span>](../../../docs/framework/app-domains/gac.md)  
 [<span data-ttu-id="a4cb3-195">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="a4cb3-195">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="a4cb3-196">명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="a4cb3-196">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
