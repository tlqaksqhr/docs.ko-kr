---
title: Mgmtclassgen.exe(강력하게 형식화된 관리 클래스 생성기)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CIM types
- Management Strongly Typed Class Generator
- WMI class
- Mgmtclassgen.exe
- early-bound managed classes
ms.assetid: 02ce6699-49b5-4a0b-b0d5-1003c491232e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 282d6376b434121ed6d59297be2ce36ce361c589
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="mgmtclassgenexe-management-strongly-typed-class-generator"></a><span data-ttu-id="ca71a-102">Mgmtclassgen.exe(강력하게 형식화된 관리 클래스 생성기)</span><span class="sxs-lookup"><span data-stu-id="ca71a-102">Mgmtclassgen.exe (Management Strongly Typed Class Generator)</span></span>
<span data-ttu-id="ca71a-103">강력하게 형식화된 관리 클래스 생성기 도구를 사용하면 지정된 WMI(Windows Management Instrumentation) 클래스에 대해 초기 바인딩 관리되는 클래스를 신속하게 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-103">The Management Strongly Typed Class Generator tool enables you to quickly generate an early-bound managed class for a specified Windows Management Instrumentation (WMI) class.</span></span> <span data-ttu-id="ca71a-104">생성된 클래스는 WMI 클래스의 인스턴스에 액세스할 때 작성해야 하는 코드를 단순화합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-104">The generated class simplifies the code you must write to access an instance of the WMI class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca71a-105">구문</span><span class="sxs-lookup"><span data-stu-id="ca71a-105">Syntax</span></span>  
  
```  
mgmtclassgen   
WMIClass [options]   
```  
  
|<span data-ttu-id="ca71a-106">인수</span><span class="sxs-lookup"><span data-stu-id="ca71a-106">Argument</span></span>|<span data-ttu-id="ca71a-107">설명</span><span class="sxs-lookup"><span data-stu-id="ca71a-107">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="ca71a-108">*WMIClass*</span><span class="sxs-lookup"><span data-stu-id="ca71a-108">*WMIClass*</span></span>|<span data-ttu-id="ca71a-109">초기 바인딩 관리되는 클래스를 생성할 Windows Management Instrumentation 클래스</span><span class="sxs-lookup"><span data-stu-id="ca71a-109">The Windows Management Instrumentation class for which to generate an early-bound managed class.</span></span>|  
  
|<span data-ttu-id="ca71a-110">옵션</span><span class="sxs-lookup"><span data-stu-id="ca71a-110">Option</span></span>|<span data-ttu-id="ca71a-111">설명</span><span class="sxs-lookup"><span data-stu-id="ca71a-111">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ca71a-112">**/l**  *language*</span><span class="sxs-lookup"><span data-stu-id="ca71a-112">**/l**  *language*</span></span>|<span data-ttu-id="ca71a-113">초기 바인딩 관리되는 클래스를 생성할 때 사용하는 언어를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-113">Specifies the language in which to generate the early-bound managed class.</span></span> <span data-ttu-id="ca71a-114">언어 인수로 **CS**(C#; default), **VB**(Visual Basic), **MC**(C++) 또는 **JS**(JScript)를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-114">You can specify **CS** (C#; default), **VB** (Visual Basic),  **MC** (C++), or **JS** (JScript) as the language argument.</span></span>|  
|<span data-ttu-id="ca71a-115">**/m**  *machine*</span><span class="sxs-lookup"><span data-stu-id="ca71a-115">**/m**  *machine*</span></span>|<span data-ttu-id="ca71a-116">WMI 클래스가 있는 연결할 컴퓨터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-116">Specifies the computer to connect to, where the WMI class resides.</span></span> <span data-ttu-id="ca71a-117">기본값은 로컬 컴퓨터입니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-117">The default is the local computer.</span></span>|  
|<span data-ttu-id="ca71a-118">**/n**  *path*</span><span class="sxs-lookup"><span data-stu-id="ca71a-118">**/n**  *path*</span></span>|<span data-ttu-id="ca71a-119">WMI 클래스가 포함된 WMI 네임스페이스의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-119">Specifies the path to the WMI namespace that contains the WMI class.</span></span> <span data-ttu-id="ca71a-120">이 옵션을 지정하지 않으면 도구에서 기본 **Root\cimv2** 네임스페이스에 *WMIClass*의 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-120">If you do not specify this option, the tool generates code for *WMIClass* in the default **Root\cimv2** namespace.</span></span>|  
|<span data-ttu-id="ca71a-121">**/o**  *classnamespace*</span><span class="sxs-lookup"><span data-stu-id="ca71a-121">**/o**  *classnamespace*</span></span>|<span data-ttu-id="ca71a-122">관리 코드 클래스를 생성할 .NET 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-122">Specifies the .NET namespace in which to generate the managed code class.</span></span> <span data-ttu-id="ca71a-123">이 옵션을 지정하지 않으면 도구에서 WMI 네임스페이스와 스키마 접두사를 사용하여 네임스페이스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-123">If you do not specify this option, the tool generates the namespace using the WMI namespace and the schema prefix.</span></span> <span data-ttu-id="ca71a-124">스키마 접두사는 밑줄 앞에 오는 클래스 이름의 일부분입니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-124">The schema prefix is the part of the class name preceding the underscore character.</span></span> <span data-ttu-id="ca71a-125">예를 들어 **Root\cimv2** 네임스페이스에 있는 **Win32_OperatingSystem** 클래스의 경우 도구에서는 **ROOT.CIMV2.Win32**에 클래스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-125">For example, for the **Win32_OperatingSystem** class in the **Root\cimv2** namespace, the tool would generate the class in **ROOT.CIMV2.Win32**.</span></span>|  
|<span data-ttu-id="ca71a-126">**/p**  *filepath*</span><span class="sxs-lookup"><span data-stu-id="ca71a-126">**/p**  *filepath*</span></span>|<span data-ttu-id="ca71a-127">생성된 코드를 저장할 파일의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-127">Specifies the path to the file in which to save the generated code.</span></span> <span data-ttu-id="ca71a-128">이 옵션을 지정하지 않으면 도구에서 현재 디렉터리에 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-128">If you do not specify this option, the tool creates the file in the current directory.</span></span> <span data-ttu-id="ca71a-129">*WMIClass* 인수를 사용하여 클래스 및 클래스를 생성한 파일의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-129">It names the class and file in which it generates the class using the *WMIClass* argument.</span></span> <span data-ttu-id="ca71a-130">클래스 이름과 파일 이름은 *WMIClass*의 이름과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-130">The name of the class and the file are the same as the name of the *WMIClass.*</span></span> <span data-ttu-id="ca71a-131">*WMIClass*에 밑줄이 있는 경우 도구에서는 밑줄 뒤에 나오는 클래스 이름 일부를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-131">If *WMIClass* contains an underscore character, the tool uses the part of the class name following the underscore character.</span></span> <span data-ttu-id="ca71a-132">예를 들어 *WMIClass* 이름이 **Win32_LogicalDisk** 형식인 경우 생성된 클래스와 파일의 이름은 "logicaldisk"입니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-132">For example, if the *WMIClass* name is in the format **Win32_LogicalDisk**, the generated class and file is named "logicaldisk".</span></span> <span data-ttu-id="ca71a-133">파일이 이미 있는 경우 도구에서는 기존 파일을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-133">If a file already exists, the tool overwrites the existing file.</span></span>|  
|<span data-ttu-id="ca71a-134">**/pw**  *password*</span><span class="sxs-lookup"><span data-stu-id="ca71a-134">**/pw**  *password*</span></span>|<span data-ttu-id="ca71a-135">**/m** 옵션으로 지정된 컴퓨터에 로그온할 때 사용할 암호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-135">Specifies the password to use when logging on to a computer specified by the **/m** option.</span></span>|  
|<span data-ttu-id="ca71a-136">**/u**  *user name*</span><span class="sxs-lookup"><span data-stu-id="ca71a-136">**/u**  *user name*</span></span>|<span data-ttu-id="ca71a-137">**/m** 옵션으로 지정된 컴퓨터에 로그온할 때 사용할 사용자 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-137">Specifies the user name to use when logging on to a computer specified by the **/m** option.</span></span>|  
|<span data-ttu-id="ca71a-138">**/?**</span><span class="sxs-lookup"><span data-stu-id="ca71a-138">**/?**</span></span>|<span data-ttu-id="ca71a-139">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-139">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca71a-140">설명</span><span class="sxs-lookup"><span data-stu-id="ca71a-140">Remarks</span></span>  
 <span data-ttu-id="ca71a-141">Mgmtclassgen.exe는 <xref:System.Management.ManagementClass.GetStronglyTypedClassCode%2A?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-141">Mgmtclassgen.exe uses the <xref:System.Management.ManagementClass.GetStronglyTypedClassCode%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ca71a-142">따라서 사용자 지정 코드 공급자를 사용하여 C#, Visual Basic 및 JScript 이외의 관리되는 언어로 코드를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-142">Therefore, you can use any custom code provider to generate code in managed languages other than C#, Visual Basic, and JScript.</span></span>  
  
 <span data-ttu-id="ca71a-143">생성된 클래스는 생성 대상인 스키마에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-143">Note that generated classes are bound to the schema for which they are generated.</span></span> <span data-ttu-id="ca71a-144">기본 스키마가 변경되는 경우 스키마의 변경 사항을 클래스에 반영하려면 클래스를 다시 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-144">If the underlying schema changes, you must regenerate the class if you want it to reflect changes to the schema.</span></span>  
  
 <span data-ttu-id="ca71a-145">다음 표에서는 WMI CIM(Common Information Model) 형식이 생성된 클래스의 데이터 형식에 어떻게 매핑되는지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-145">The following table shows how WMI Common Information Model (CIM) types map to data types in a generated class:</span></span>  
  
|<span data-ttu-id="ca71a-146">CIM 형식</span><span class="sxs-lookup"><span data-stu-id="ca71a-146">CIM type</span></span>|<span data-ttu-id="ca71a-147">생성된 클래스의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ca71a-147">Data type in the generated class</span></span>|  
|--------------|--------------------------------------|  
|<span data-ttu-id="ca71a-148">CIM_SINT8</span><span class="sxs-lookup"><span data-stu-id="ca71a-148">CIM_SINT8</span></span>|<span data-ttu-id="ca71a-149">**SByte**</span><span class="sxs-lookup"><span data-stu-id="ca71a-149">**SByte**</span></span>|  
|<span data-ttu-id="ca71a-150">CIM_UINT8</span><span class="sxs-lookup"><span data-stu-id="ca71a-150">CIM_UINT8</span></span>|<span data-ttu-id="ca71a-151">**Byte**</span><span class="sxs-lookup"><span data-stu-id="ca71a-151">**Byte**</span></span>|  
|<span data-ttu-id="ca71a-152">CIM_SINT16</span><span class="sxs-lookup"><span data-stu-id="ca71a-152">CIM_SINT16</span></span>|<span data-ttu-id="ca71a-153">**Int16**</span><span class="sxs-lookup"><span data-stu-id="ca71a-153">**Int16**</span></span>|  
|<span data-ttu-id="ca71a-154">CIM_UINT16</span><span class="sxs-lookup"><span data-stu-id="ca71a-154">CIM_UINT16</span></span>|<span data-ttu-id="ca71a-155">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="ca71a-155">**UInt16**</span></span>|  
|<span data-ttu-id="ca71a-156">CIM_SINT32</span><span class="sxs-lookup"><span data-stu-id="ca71a-156">CIM_SINT32</span></span>|<span data-ttu-id="ca71a-157">**Int32**</span><span class="sxs-lookup"><span data-stu-id="ca71a-157">**Int32**</span></span>|  
|<span data-ttu-id="ca71a-158">SIM_UINT32</span><span class="sxs-lookup"><span data-stu-id="ca71a-158">SIM_UINT32</span></span>|<span data-ttu-id="ca71a-159">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="ca71a-159">**UInt32**</span></span>|  
|<span data-ttu-id="ca71a-160">CIM_SINT64</span><span class="sxs-lookup"><span data-stu-id="ca71a-160">CIM_SINT64</span></span>|<span data-ttu-id="ca71a-161">**Int64**</span><span class="sxs-lookup"><span data-stu-id="ca71a-161">**Int64**</span></span>|  
|<span data-ttu-id="ca71a-162">CIM_UINT64</span><span class="sxs-lookup"><span data-stu-id="ca71a-162">CIM_UINT64</span></span>|<span data-ttu-id="ca71a-163">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="ca71a-163">**UInt64**</span></span>|  
|<span data-ttu-id="ca71a-164">CIM_REAL32</span><span class="sxs-lookup"><span data-stu-id="ca71a-164">CIM_REAL32</span></span>|<span data-ttu-id="ca71a-165">**Single**</span><span class="sxs-lookup"><span data-stu-id="ca71a-165">**Single**</span></span>|  
|<span data-ttu-id="ca71a-166">CIM_REAL64</span><span class="sxs-lookup"><span data-stu-id="ca71a-166">CIM_REAL64</span></span>|<span data-ttu-id="ca71a-167">**Double**</span><span class="sxs-lookup"><span data-stu-id="ca71a-167">**Double**</span></span>|  
|<span data-ttu-id="ca71a-168">CIM_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="ca71a-168">CIM_BOOLEAN</span></span>|<span data-ttu-id="ca71a-169">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="ca71a-169">**Boolean**</span></span>|  
|<span data-ttu-id="ca71a-170">CIM_String</span><span class="sxs-lookup"><span data-stu-id="ca71a-170">CIM_String</span></span>|<span data-ttu-id="ca71a-171">**String**</span><span class="sxs-lookup"><span data-stu-id="ca71a-171">**String**</span></span>|  
|<span data-ttu-id="ca71a-172">CIM_DATETIME</span><span class="sxs-lookup"><span data-stu-id="ca71a-172">CIM_DATETIME</span></span>|<span data-ttu-id="ca71a-173">**DateTime** 또는 **TimeSpan**</span><span class="sxs-lookup"><span data-stu-id="ca71a-173">**DateTime** or **TimeSpan**</span></span>|  
|<span data-ttu-id="ca71a-174">CIM_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="ca71a-174">CIM_REFERENCE</span></span>|<span data-ttu-id="ca71a-175">**ManagementPath**</span><span class="sxs-lookup"><span data-stu-id="ca71a-175">**ManagementPath**</span></span>|  
|<span data-ttu-id="ca71a-176">CIM_CHAR16</span><span class="sxs-lookup"><span data-stu-id="ca71a-176">CIM_CHAR16</span></span>|<span data-ttu-id="ca71a-177">**Char**</span><span class="sxs-lookup"><span data-stu-id="ca71a-177">**Char**</span></span>|  
|<span data-ttu-id="ca71a-178">CIM_OBJECT</span><span class="sxs-lookup"><span data-stu-id="ca71a-178">CIM_OBJECT</span></span>|<span data-ttu-id="ca71a-179">**ManagementBaseObject**</span><span class="sxs-lookup"><span data-stu-id="ca71a-179">**ManagementBaseObject**</span></span>|  
|<span data-ttu-id="ca71a-180">CIM_IUNKNOWN</span><span class="sxs-lookup"><span data-stu-id="ca71a-180">CIM_IUNKNOWN</span></span>|<span data-ttu-id="ca71a-181">**개체**</span><span class="sxs-lookup"><span data-stu-id="ca71a-181">**Object**</span></span>|  
|<span data-ttu-id="ca71a-182">CIM_ARRAY</span><span class="sxs-lookup"><span data-stu-id="ca71a-182">CIM_ARRAY</span></span>|<span data-ttu-id="ca71a-183">위에 명시된 개체의 배열</span><span class="sxs-lookup"><span data-stu-id="ca71a-183">Array of the above mentioned objects</span></span>|  
  
 <span data-ttu-id="ca71a-184">WMI 클래스를 생성할 때는 다음 사항에 유의하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca71a-184">Note the following behaviors when you generate a WMI class:</span></span>  
  
-   <span data-ttu-id="ca71a-185">표준 공용 속성이나 메서드의 이름이 기존 속성이나 메서드의 이름과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-185">It is possible for a standard public property or method to have the same name as an existing property or method.</span></span> <span data-ttu-id="ca71a-186">이런 경우에는 도구에서 이름 충돌을 방지하기 위해 생성된 클래스에 있는 속성이나 메서드의 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-186">If this occurs, the tool changes the name of the property or method in the generated class to avoid naming conflicts.</span></span>  
  
-   <span data-ttu-id="ca71a-187">생성된 클래스에 있는 속성이나 메서드의 이름이 대상 프로그래밍 언어의 키워드일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-187">It is possible for the name of a property or method in a generated class to be a keyword in the target programming language.</span></span> <span data-ttu-id="ca71a-188">이런 경우에는 도구에서 이름 충돌을 방지하기 위해 생성된 클래스에 있는 속성이나 메서드의 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-188">If this occurs, the tool changes the name of the property or method in the generated class to avoid naming conflicts.</span></span>  
  
-   <span data-ttu-id="ca71a-189">WMI에서 한정자에는 클래스, 인스턴스, 속성 또는 메서드를 설명하는 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-189">In WMI, qualifiers are modifiers that contain information to describe a class, instance, property, or method.</span></span> <span data-ttu-id="ca71a-190">WMI에서는 **Read**, **Write**, **Key** 등의 표준 한정자를 사용하여 생성된 클래스의 속성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-190">WMI uses standard qualifiers such as **Read**, **Write**, and **Key** to describe a property in a generated class.</span></span> <span data-ttu-id="ca71a-191">예를 들어 **Read** 한정자로 한정되는 속성은 생성된 클래스에서 속성 **get** 접근자를 통해서만 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-191">For example, a property that is modified with a **Read** qualifier is defined only with a property **get** accessor in the generated class.</span></span> <span data-ttu-id="ca71a-192">**Read** 한정자로 표시된 속성은 읽기 전용이므로 **set** 접근자가 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-192">Because a property marked with the **Read** qualifier is intended to be read-only, a **set** accessor is not defined.</span></span>  
  
-   <span data-ttu-id="ca71a-193">숫자 속성은 지정된 허용 값으로만 설정될 수 있음을 나타내기 위해 **Values** 및 **ValueMaps** 한정자를 사용하여 한정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-193">A numeric property can be modified by the **Values** and **ValueMaps** qualifiers to indicate that the property can be set only to specified permissible values.</span></span> <span data-ttu-id="ca71a-194">열거형이 이러한 **Values** 및 **ValueMaps**와 함께 생성되며 속성은 이 열거형으로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-194">An enumeration is generated with these **Values** and **ValueMaps** and the property is mapped to the enumeration.</span></span>  
  
-   <span data-ttu-id="ca71a-195">WMI에서는 singleton이라는 용어를 사용하여 인스턴스를 하나만 갖는 클래스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-195">The WMI uses the term singleton to describe a class that can have only one instance.</span></span> <span data-ttu-id="ca71a-196">따라서 singleton 클래스의 기본 생성자는 클래스를 해당 클래스의 유일한 인스턴스로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-196">Therefore, the default constructor for a singleton class will initialize the class to the only instance of the class.</span></span>  
  
-   <span data-ttu-id="ca71a-197">WMI 클래스에는 개체인 속성이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-197">A WMI class can have properties that are objects.</span></span> <span data-ttu-id="ca71a-198">이러한 유형의 WMI 클래스에 대한 강력한 형식의 클래스를 생성하는 경우 포함된 개체 속성의 형식에 대한 강력한 형식의 클래스를 생성할 것을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-198">When you generate a strongly-typed class for this type of WMI class, you should consider generating strongly-typed classes for the types of the embedded object properties.</span></span> <span data-ttu-id="ca71a-199">이렇게 하면 포함된 개체에 강력한 형식을 사용하여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-199">This will allow you to access the embedded objects in a strongly-typed manner.</span></span> <span data-ttu-id="ca71a-200">생성된 코드는 포함된 개체의 형식을 감지하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-200">Note that the generated code might not be able to detect the type of the embedded object.</span></span> <span data-ttu-id="ca71a-201">이런 경우 이 문제를 알려 주는 주석이 생성된 코드 안에 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-201">In this case, a comment will be created in the generated code to notify you of this issue.</span></span> <span data-ttu-id="ca71a-202">따라서 생성된 코드를 수정하여 생성된 다른 클래스에 속성을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-202">You can then modify the generated code to type the property to the other generated class.</span></span>  
  
-   <span data-ttu-id="ca71a-203">WMI에서는 CIM_DATETIME 데이터 형식의 데이터 값을 특정 날짜 및 시간이나 시간 간격으로 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-203">In WMI, the data value of the CIM_DATETIME data type can represent either a specific date and time or a time interval.</span></span> <span data-ttu-id="ca71a-204">데이터 값이 날짜 및 시간을 나타내는 경우 생성된 클래스의 데이터 형식은 **DateTime**이 되고,</span><span class="sxs-lookup"><span data-stu-id="ca71a-204">If the data value represents a date and time, the data type in the generated class is **DateTime**.</span></span> <span data-ttu-id="ca71a-205">데이터 값이 시간 간격을 나타내는 경우 생성된 클래스의 데이터 형식은 **TimeSpan**이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-205">If the data value represents a time interval, the data type in the generated class is **TimeSpan**.</span></span>  
  
 <span data-ttu-id="ca71a-206">또는 Visual Studio .NET의 Server Explorer Management Extension을 사용하여 강력한 형식의 클래스를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-206">You can alternately generate a strongly-typed class using the Server Explorer Management Extension in Visual Studio .NET.</span></span>  
  
 <span data-ttu-id="ca71a-207">WMI에 대한 자세한 내용은 Platform SDK 설명서의 **WMI(Windows Management Instrumentation)** 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca71a-207">For more information about WMI, see the **Windows Management Instrumentation** topic in the Platform SDK documentation.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="ca71a-208">예제</span><span class="sxs-lookup"><span data-stu-id="ca71a-208">Examples</span></span>  
 <span data-ttu-id="ca71a-209">다음 명령은 C# 코드로 **Root\cimv2** 네임스페이스의 **Win32_LogicalDisk** WMI 클래스에 대한 관리되는 클래스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-209">The following command generates a managed class in C# code for the **Win32_LogicalDisk** WMI class in the **Root\cimv2** namespace.</span></span> <span data-ttu-id="ca71a-210">도구에서 관리되는 클래스를 **ROOT.CIMV2.Win32** 네임스페이스의 c:\disk.cs에 소스 파일로 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-210">The tool writes the managed class to the source file at c:\disk.cs in the **ROOT.CIMV2.Win32** namespace.</span></span>  
  
```  
mgmtclassgen Win32_LogicalDisk /n root\cimv2 /l CS /p c:\disk.cs  
```  
  
 <span data-ttu-id="ca71a-211">다음 코드 예제에서는 생성된 클래스를 프로그래밍 방식으로 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-211">The following code example shows how to use a generated class programmatically.</span></span> <span data-ttu-id="ca71a-212">첫째, 클래스의 인스턴스가 열거되고 경로가 인쇄됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-212">First, an instance of the class is enumerated and the path is printed.</span></span> <span data-ttu-id="ca71a-213">그런 다음, 초기화할 생성된 클래스의 인스턴스는 WMI의 인스턴스를 사용하여 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-213">Next, an instance of the generated class to be initialized is created with an instance of WMI.</span></span> <span data-ttu-id="ca71a-214">`Process`는 **Win32_Process**에 대해 생성된 클래스이고 `LogicalDisk`는 **Root\cimv2** 네임스페이스에서 **Win32_LogicalDisk**에 대해 생성된 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ca71a-214">`Process` is the class generated for **Win32_Process** and `LogicalDisk` is the class generated for **Win32_LogicalDisk** in the **Root\cimv2** namespace.</span></span>  
  
```vb  
Imports System  
Imports System.Management  
Imports ROOT.CIMV2.Win32  
  
Public Class App     
   Public Shared Sub Main()        
      ' Enumerate instances of the Win32_process.  
      ' Print the Name property of the instance.  
      Dim ps As Process     
      For Each ps In  Process.GetInstances()  
         Console.WriteLine(ps.Name)  
      Next ps  
  
      ' Initialize the instance of LogicalDisk with  
      ' the WMI instance pointing to logical drive d:.  
      Dim dskD As New LogicalDisk(New _  
         ManagementPath("win32_LogicalDisk.DeviceId=""d:"""))  
      Console.WriteLine(dskD.Caption)  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Management;  
using ROOT.CIMV2.Win32;  
  
public class App  
{  
   public static void Main()  
   {  
      // Enumerate instances of the Win32_process.  
      // Print the Name property of the instance.  
      foreach(Process ps in Process.GetInstances())  
      {  
         Console.WriteLine(ps.Name);  
      }  
  
      // Initialize the instance of LogicalDisk with  
      // the WMI instance pointing to logical drive d:.  
      LogicalDisk dskD = new LogicalDisk(new ManagementPath(  
        "win32_LogicalDisk.DeviceId=\"d:\""));  
      Console.WriteLine(dskD.Caption);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca71a-215">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca71a-215">See Also</span></span>  
 <xref:System.Management>  
 <xref:System.Management.ManagementClass.GetStronglyTypedClassCode%2A?displayProperty=nameWithType>  
 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>  
 [<span data-ttu-id="ca71a-216">도구</span><span class="sxs-lookup"><span data-stu-id="ca71a-216">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="ca71a-217">명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="ca71a-217">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
