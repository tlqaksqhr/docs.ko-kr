---
title: -appconfig(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /appconfig
helpviewer_keywords:
- /appconfig compiler option [C#]
- -appconfig compiler option [C#]
- appconfig compiler option [C#]
ms.assetid: 1cdbcbcc-7813-4010-b5b8-e67c107c5a98
ms.openlocfilehash: 3fca0821b8665354d840783fca3ab90ece41b2cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33214772"
---
# <a name="-appconfig-c-compiler-options"></a><span data-ttu-id="54b45-102">-appconfig(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="54b45-102">-appconfig (C# Compiler Options)</span></span>
<span data-ttu-id="54b45-103">**-appconfig** 컴파일러 옵션을 사용하면 C# 응용 프로그램이 어셈블리 바인딩 시간에 어셈블리의 응용 프로그램 구성(app.config) 파일 위치를 CLR(공용 언어 런타임)에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b45-103">The **-appconfig** compiler option enables a C# application to specify the location of an assembly's application configuration (app.config) file to the common language runtime (CLR) at assembly binding time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54b45-104">구문</span><span class="sxs-lookup"><span data-stu-id="54b45-104">Syntax</span></span>  
  
```console  
-appconfig:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="54b45-105">인수</span><span class="sxs-lookup"><span data-stu-id="54b45-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="54b45-106">필수.</span><span class="sxs-lookup"><span data-stu-id="54b45-106">Required.</span></span> <span data-ttu-id="54b45-107">어셈블리 바인딩 설정이 포함된 응용 프로그램 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="54b45-107">The application configuration file that contains assembly binding settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54b45-108">설명</span><span class="sxs-lookup"><span data-stu-id="54b45-108">Remarks</span></span>  
 <span data-ttu-id="54b45-109">**-appconfig**의 한 가지 용도는 어셈블리가 특정 참조 어셈블리의 .NET Framework 버전과 .NET Framework for Silverlight 버전을 동시에 둘 다 참조해야 하는 고급 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="54b45-109">One use of **-appconfig** is advanced scenarios in which an assembly has to reference both the .NET Framework version and the .NET Framework for Silverlight version of a particular reference assembly at the same time.</span></span> <span data-ttu-id="54b45-110">예를 들어 WPF(Windows Presentation Foundation)로 작성된 XAML 디자이너는 디자이너의 사용자 인터페이스를 위한 WPF 데스크톱 및 Silverlight에 포함된 WPF 하위 집합을 둘 다 참조해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b45-110">For example, a XAML designer written in Windows Presentation Foundation (WPF) might have to reference both the WPF Desktop, for the designer's user interface, and the subset of WPF that is included with Silverlight.</span></span> <span data-ttu-id="54b45-111">같은 디자이너 어셈블리가 두 어셈블리에 모두 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b45-111">The same designer assembly has to access both assemblies.</span></span> <span data-ttu-id="54b45-112">기본적으로, 어셈블리 바인딩 시 두 어셈블리가 동등한 것으로 간주되기 때문에 서로 다른 참조를 사용할 경우 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="54b45-112">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span>  
  
 <span data-ttu-id="54b45-113">**-appconfig** 컴파일러 옵션을 사용하면 다음 예제와 같이 `<supportPortability>` 태그를 사용하여 기본 동작을 비활성화하는 app.config 파일의 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b45-113">The **-appconfig** compiler option enables you to specify the location of an app.config file that disables the default behavior by using a `<supportPortability>` tag, as shown in the following example.</span></span>  
  
 `<supportPortability PKT="7cec85d7bea7798e" enable="false"/>`  
  
 <span data-ttu-id="54b45-114">컴파일러는 이 파일 위치를 CLR의 어셈블리 바인딩 논리에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="54b45-114">The compiler passes the location of the file to the CLR's assembly-binding logic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54b45-115">Microsoft Build Engine(MSBuild)을 사용하여 응용 프로그램을 빌드하는 경우 .csproj 파일에 속성 태그를 추가하여 **-appconfig** 컴파일러 옵션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b45-115">If you are using the Microsoft Build Engine (MSBuild) to build your application, you can set the **-appconfig** compiler option by adding a property tag to the .csproj file.</span></span> <span data-ttu-id="54b45-116">프로젝트에 이미 설정된 app.config 파일을 사용하려면 속성 태그 `<UseAppConfigForCompiler>`를 .csproj 파일에 추가하고 해당 값을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="54b45-116">To use the app.config file that is already set in the project, add property tag `<UseAppConfigForCompiler>` to the .csproj file and set its value to `true`.</span></span> <span data-ttu-id="54b45-117">다른 app.config 파일을 지정하려면 속성 태그 `<AppConfigForCompiler>`를 추가하고 해당 값을 파일 위치로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="54b45-117">To specify a different app.config file, add property tag `<AppConfigForCompiler>` and set its value to the location of the file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54b45-118">예</span><span class="sxs-lookup"><span data-stu-id="54b45-118">Example</span></span>  
 <span data-ttu-id="54b45-119">다음 예제에서는 응용 프로그램이 두 구현에 모두 있는 .NET Framework 어셈블리의 .NET Framework for Silverlight 구현과 .NET Framework 구현 둘 다에 대한 참조를 사용할 수 있도록 하는 app.config 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="54b45-119">The following example shows an app.config file that enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="54b45-120">**-appconfig** 컴파일러 옵션은 이 app.config 파일의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="54b45-120">The **-appconfig** compiler option specifies the location of this app.config file.</span></span>  
  
```xml  
<configuration>  
      <runtime>  
      <assemblyBinding>  
            <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
            <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
      </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="54b45-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54b45-121">See Also</span></span>  
 [<span data-ttu-id="54b45-122">\<supportPortability> 요소</span><span class="sxs-lookup"><span data-stu-id="54b45-122">\<supportPortability> Element</span></span>](../../../framework/configure-apps/file-schema/runtime/supportportability-element.md)  
 [<span data-ttu-id="54b45-123">사전순 C# 컴파일러 옵션 목록</span><span class="sxs-lookup"><span data-stu-id="54b45-123">C# Compiler Options Listed Alphabetically</span></span>](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)
