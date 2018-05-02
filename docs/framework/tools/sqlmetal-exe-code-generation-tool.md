---
title: SqlMetal.exe(코드 생성 도구)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQLMetal [LINQ to SQL]
- code generation tool
- SQLMetal.exe
- LINQ to SQL, serialization
- LINQ to SQL, DBML files
- LINQ to SQL, SQLMetal
ms.assetid: 819e5a96-7646-4fdb-b14b-fe31221b0614
caps.latest.revision: 43
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5c21c08cf76143959d11498594fbc94fb1dac55c
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="sqlmetalexe-code-generation-tool"></a><span data-ttu-id="832ec-102">SqlMetal.exe(코드 생성 도구)</span><span class="sxs-lookup"><span data-stu-id="832ec-102">SqlMetal.exe (Code Generation Tool)</span></span>
<span data-ttu-id="832ec-103">SqlMetal 명령줄 도구는 [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] 의 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]구성 요소에 사용할 코드 및 매핑을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-103">The SqlMetal command-line tool generates code and mapping for the [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] component of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="832ec-104">이 항목의 뒷부분에 나오는 옵션을 적용하면 SqlMetal을 통해 다음을 포함하는 다양한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-104">By applying options that appear later in this topic, you can instruct SqlMetal to perform several different actions that include the following:</span></span>  
  
-   <span data-ttu-id="832ec-105">데이터베이스에서 소스 코드 및 매핑 특성이나 매핑 파일 생성</span><span class="sxs-lookup"><span data-stu-id="832ec-105">From a database, generate source code and mapping attributes or a mapping file.</span></span>  
  
-   <span data-ttu-id="832ec-106">데이터베이스에서 사용자 지정에 사용할 중간 데이터베이스 태그 언어(.dbml) 파일 생성</span><span class="sxs-lookup"><span data-stu-id="832ec-106">From a database, generate an intermediate database markup language (.dbml) file for customization.</span></span>  
  
-   <span data-ttu-id="832ec-107">.dbml 파일에서 코드 및 매핑 특성이나 매핑 파일 생성</span><span class="sxs-lookup"><span data-stu-id="832ec-107">From a .dbml file, generate code and mapping attributes or a mapping file.</span></span>  
  
 <span data-ttu-id="832ec-108">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-108">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="832ec-109">기본적으로 이 파일은 `drive`:\Program Files\Microsoft SDKs\Windows\v`n.nn`\bin에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-109">By default, the file is located at `drive`:\Program Files\Microsoft SDKs\Windows\v`n.nn`\bin.</span></span> <span data-ttu-id="832ec-110">Visual Studio를 설치하지 않으면 [Windows SDK](http://go.microsoft.com/fwlink/?LinkId=142225)를 다운로드하여 SQLMetal 파일도 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-110">If you do not install Visual Studio, you can also get the SQLMetal file by downloading the [Windows SDK](http://go.microsoft.com/fwlink/?LinkId=142225).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="832ec-111">[!INCLUDE[vs_ordesigner_long](../../../includes/vs-ordesigner-long-md.md)] 를 사용하는 개발자는 Visual Studio를 사용하여 엔터티 클래스를 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-111">Developers who use Visual Studio can also use the [!INCLUDE[vs_ordesigner_long](../../../includes/vs-ordesigner-long-md.md)] to generate entity classes.</span></span> <span data-ttu-id="832ec-112">명령줄 방식을 사용하면 대규모 데이터베이스에 대해 효율적으로 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-112">The command-line approach scales well for large databases.</span></span> <span data-ttu-id="832ec-113">SqlMetal은 명령줄 도구이므로 빌드 프로세스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-113">Because SqlMetal is a command-line tool, you can use it in a build process.</span></span>  
  
 <span data-ttu-id="832ec-114">이 도구를 실행하려면 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-114">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="832ec-115">자세한 내용은 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)를 참조하세요. 명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-115">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="832ec-116">구문</span><span class="sxs-lookup"><span data-stu-id="832ec-116">Syntax</span></span>  
  
```  
sqlmetal [options] [<input file>]  
```  
  
## <a name="options"></a><span data-ttu-id="832ec-117">옵션</span><span class="sxs-lookup"><span data-stu-id="832ec-117">Options</span></span>  
 <span data-ttu-id="832ec-118">최신 옵션 목록을 보려면 설치한 위치의 명령 프롬프트에서 `sqlmetal /?` 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-118">To view the most current option list, type `sqlmetal /?` at a command prompt from the installed location.</span></span>  
  
 <span data-ttu-id="832ec-119">**연결 옵션**</span><span class="sxs-lookup"><span data-stu-id="832ec-119">**Connection Options**</span></span>  
  
|<span data-ttu-id="832ec-120">옵션</span><span class="sxs-lookup"><span data-stu-id="832ec-120">Option</span></span>|<span data-ttu-id="832ec-121">설명</span><span class="sxs-lookup"><span data-stu-id="832ec-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="832ec-122">**/server:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="832ec-122">**/server:** *\<name>*</span></span>|<span data-ttu-id="832ec-123">데이터베이스 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-123">Specifies database server name.</span></span>|  
|<span data-ttu-id="832ec-124">**/database:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="832ec-124">**/database:** *\<name>*</span></span>|<span data-ttu-id="832ec-125">서버의 데이터베이스 카탈로그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-125">Specifies database catalog on server.</span></span>|  
|<span data-ttu-id="832ec-126">**/user:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="832ec-126">**/user:** *\<name>*</span></span>|<span data-ttu-id="832ec-127">로그온 사용자 ID를 지정합니다. 기본적으로는 Windows 인증이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-127">Specifies logon user id. Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="832ec-128">**/password:** *\<password>*</span><span class="sxs-lookup"><span data-stu-id="832ec-128">**/password:** *\<password>*</span></span>|<span data-ttu-id="832ec-129">로그온 암호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-129">Specifies logon password.</span></span> <span data-ttu-id="832ec-130">기본적으로는 Windows 인증이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-130">Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="832ec-131">**/conn:** *\<connection string>*</span><span class="sxs-lookup"><span data-stu-id="832ec-131">**/conn:** *\<connection string>*</span></span>|<span data-ttu-id="832ec-132">데이터베이스 연결 문자열을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-132">Specifies database connection string.</span></span> <span data-ttu-id="832ec-133">**/server**, **/database**, **/user**또는 **/password** 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-133">Cannot be used with **/server**, **/database**, **/user**, or **/password** options.</span></span><br /><br /> <span data-ttu-id="832ec-134">연결 문자열에 파일 이름을 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="832ec-134">Do not include the file name in the connection string.</span></span> <span data-ttu-id="832ec-135">대신 파일 이름을 명령줄에 입력 파일로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-135">Instead, add the file name to the command line as the input file.</span></span> <span data-ttu-id="832ec-136">예를 들어 **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"** 에서는 "c:\northwnd.mdf"를 입력 파일로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-136">For example, the following line specifies "c:\northwnd.mdf" as the input file: **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"**.</span></span>|  
|<span data-ttu-id="832ec-137">**/timeout:** *\<seconds>*</span><span class="sxs-lookup"><span data-stu-id="832ec-137">**/timeout:** *\<seconds>*</span></span>|<span data-ttu-id="832ec-138">SqlMetal이 데이터베이스에 액세스할 때의 시간 제한 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-138">Specifies time-out value when SqlMetal accesses the database.</span></span> <span data-ttu-id="832ec-139">기본값은 0(시간 제한 없음)입니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-139">Default value: 0 (that is, no time limit).</span></span>|  
  
 <span data-ttu-id="832ec-140">**추출 옵션**</span><span class="sxs-lookup"><span data-stu-id="832ec-140">**Extraction options**</span></span>  
  
|<span data-ttu-id="832ec-141">옵션</span><span class="sxs-lookup"><span data-stu-id="832ec-141">Option</span></span>|<span data-ttu-id="832ec-142">설명</span><span class="sxs-lookup"><span data-stu-id="832ec-142">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="832ec-143">**/views**</span><span class="sxs-lookup"><span data-stu-id="832ec-143">**/views**</span></span>|<span data-ttu-id="832ec-144">데이터베이스 뷰를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-144">Extracts database views.</span></span>|  
|<span data-ttu-id="832ec-145">**/functions**</span><span class="sxs-lookup"><span data-stu-id="832ec-145">**/functions**</span></span>|<span data-ttu-id="832ec-146">데이터베이스 기능을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-146">Extracts database functions.</span></span>|  
|<span data-ttu-id="832ec-147">**/sprocs**</span><span class="sxs-lookup"><span data-stu-id="832ec-147">**/sprocs**</span></span>|<span data-ttu-id="832ec-148">저장 프로시저를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-148">Extracts stored procedures.</span></span>|  
  
 <span data-ttu-id="832ec-149">**출력 옵션**</span><span class="sxs-lookup"><span data-stu-id="832ec-149">**Output options**</span></span>  
  
|<span data-ttu-id="832ec-150">옵션</span><span class="sxs-lookup"><span data-stu-id="832ec-150">Option</span></span>|<span data-ttu-id="832ec-151">설명</span><span class="sxs-lookup"><span data-stu-id="832ec-151">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="832ec-152">**/dbml** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="832ec-152">**/dbml** *[:file]*</span></span>|<span data-ttu-id="832ec-153">출력을 .dbml로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-153">Sends output as .dbml.</span></span> <span data-ttu-id="832ec-154">**/map** 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-154">Cannot be used with **/map** option.</span></span>|  
|<span data-ttu-id="832ec-155">**/code** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="832ec-155">**/code** *[:file]*</span></span>|<span data-ttu-id="832ec-156">출력을 소스 코드로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-156">Sends output as source code.</span></span> <span data-ttu-id="832ec-157">**/dbml** 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-157">Cannot be used with **/dbml** option.</span></span>|  
|<span data-ttu-id="832ec-158">**/map** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="832ec-158">**/map** *[:file]*</span></span>|<span data-ttu-id="832ec-159">특성 대신 XML 매핑 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-159">Generates an XML mapping file instead of attributes.</span></span> <span data-ttu-id="832ec-160">**/dbml** 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-160">Cannot be used with **/dbml** option.</span></span>|  
  
 <span data-ttu-id="832ec-161">**기타**</span><span class="sxs-lookup"><span data-stu-id="832ec-161">**Miscellaneous**</span></span>  
  
|<span data-ttu-id="832ec-162">옵션</span><span class="sxs-lookup"><span data-stu-id="832ec-162">Option</span></span>|<span data-ttu-id="832ec-163">설명</span><span class="sxs-lookup"><span data-stu-id="832ec-163">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="832ec-164">**/language:** *\<language>*</span><span class="sxs-lookup"><span data-stu-id="832ec-164">**/language:** *\<language>*</span></span>|<span data-ttu-id="832ec-165">소스 코드 언어를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-165">Specifies source code language.</span></span><br /><br /> <span data-ttu-id="832ec-166">유효한 *\<language>*: vb, csharp.</span><span class="sxs-lookup"><span data-stu-id="832ec-166">Valid *\<language>*: vb, csharp.</span></span><br /><br /> <span data-ttu-id="832ec-167">기본적으로 이 언어는 코드 파일 이름의 확장명에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-167">Default value: Derived from extension on code file name.</span></span>|  
|<span data-ttu-id="832ec-168">**/namespace:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="832ec-168">**/namespace:** *\<name>*</span></span>|<span data-ttu-id="832ec-169">생성된 코드의 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-169">Specifies namespace of the generated code.</span></span> <span data-ttu-id="832ec-170">기본적으로는 네임스페이스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-170">Default value: no namespace.</span></span>|  
|<span data-ttu-id="832ec-171">**/context:** *\<type>*</span><span class="sxs-lookup"><span data-stu-id="832ec-171">**/context:** *\<type>*</span></span>|<span data-ttu-id="832ec-172">데이터 컨텍스트 클래스의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-172">Specifies name of data context class.</span></span> <span data-ttu-id="832ec-173">기본적으로 이 이름은 데이터베이스 이름에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-173">Default value: Derived from database name.</span></span>|  
|<span data-ttu-id="832ec-174">**/entitybase:** *\<type>*</span><span class="sxs-lookup"><span data-stu-id="832ec-174">**/entitybase:** *\<type>*</span></span>|<span data-ttu-id="832ec-175">생성된 코드에서 엔터티 클래스의 기본 클래스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-175">Specifies the base class of the entity classes in the generated code.</span></span> <span data-ttu-id="832ec-176">기본적으로 엔터티에는 기본 클래스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-176">Default value: Entities have no base class.</span></span>|  
|<span data-ttu-id="832ec-177">**/pluralize**</span><span class="sxs-lookup"><span data-stu-id="832ec-177">**/pluralize**</span></span>|<span data-ttu-id="832ec-178">클래스 및 멤버 이름을 자동으로 복수 및 단수로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-178">Automatically pluralizes or singularizes class and member names.</span></span><br /><br /> <span data-ttu-id="832ec-179">이 옵션은 미국에서만 사용할 수 있습니다. 영어 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-179">This option is available only in the U.S. English version.</span></span>|  
|<span data-ttu-id="832ec-180">**/serialization:** *\<option>*</span><span class="sxs-lookup"><span data-stu-id="832ec-180">**/serialization:** *\<option>*</span></span>|<span data-ttu-id="832ec-181">serialize 가능한 클래스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-181">Generates serializable classes.</span></span><br /><br /> <span data-ttu-id="832ec-182">유효한 *\<option>*: None, Unidirectional.</span><span class="sxs-lookup"><span data-stu-id="832ec-182">Valid *\<option>*: None, Unidirectional.</span></span> <span data-ttu-id="832ec-183">기본값은 None입니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-183">Default value: None.</span></span><br /><br /> <span data-ttu-id="832ec-184">자세한 내용은 [Serialization](../../../docs/framework/data/adonet/sql/linq/serialization.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="832ec-184">For more information, see [Serialization](../../../docs/framework/data/adonet/sql/linq/serialization.md).</span></span>|  
  
 <span data-ttu-id="832ec-185">**입력 파일**</span><span class="sxs-lookup"><span data-stu-id="832ec-185">**Input File**</span></span>  
  
|<span data-ttu-id="832ec-186">옵션</span><span class="sxs-lookup"><span data-stu-id="832ec-186">Option</span></span>|<span data-ttu-id="832ec-187">설명</span><span class="sxs-lookup"><span data-stu-id="832ec-187">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="832ec-188">**\<input file>**</span><span class="sxs-lookup"><span data-stu-id="832ec-188">**\<input file>**</span></span>|<span data-ttu-id="832ec-189">SQL Server Express .mdf 파일, [!INCLUDE[ssEW](../../../includes/ssew-md.md)] .sdf 파일 또는 .dbml 중간 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-189">Specifies a SQL Server Express .mdf file, a [!INCLUDE[ssEW](../../../includes/ssew-md.md)] .sdf file, or a .dbml intermediate file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="832ec-190">설명</span><span class="sxs-lookup"><span data-stu-id="832ec-190">Remarks</span></span>  
 <span data-ttu-id="832ec-191">실제로 SqlMetal 기능에는 다음과 같은 두 단계가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-191">SqlMetal functionality actually involves two steps:</span></span>  
  
-   <span data-ttu-id="832ec-192">데이터베이스의 메타데이터를 .dbml 파일에 추출</span><span class="sxs-lookup"><span data-stu-id="832ec-192">Extracting the metadata of the database into a .dbml file.</span></span>  
  
-   <span data-ttu-id="832ec-193">코드 출력 파일 생성</span><span class="sxs-lookup"><span data-stu-id="832ec-193">Generating a code output file.</span></span>  
  
     <span data-ttu-id="832ec-194">적절한 명령줄 옵션을 사용하면 Visual Basic 또는 C# 소스 코드를 생성하거나 XML 매핑 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-194">By using the appropriate command-line options, you can produce Visual Basic or C# source code, or you can produce an XML mapping file.</span></span>  
  
 <span data-ttu-id="832ec-195">.mdf 파일에서 메타데이터를 추출하려면 다른 모든 옵션 뒤에 .mdf 파일 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-195">To extract the metadata from an .mdf file, you must specify the name of the .mdf file after all other options.</span></span>  
  
 <span data-ttu-id="832ec-196">**/server** 가 지정되어 있지 않으면 **localhost/sqlexpress** 로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-196">If no **/server** is specified, **localhost/sqlexpress** is assumed.</span></span>  
  
 <span data-ttu-id="832ec-197">다음 조건 중 하나 이상이 true이면[!INCLUDE[sqprsqext](../../../includes/sqprsqext-md.md)] 는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-197">[!INCLUDE[sqprsqext](../../../includes/sqprsqext-md.md)] throws an exception if one or more of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="832ec-198">SqlMetal이 자기 자신을 호출하는 저장 프로시저의 추출을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-198">SqlMetal tries to extract a stored procedure that calls itself.</span></span>  
  
-   <span data-ttu-id="832ec-199">저장 프로시저, 함수 또는 뷰의 중첩 수준이 32를 초과합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-199">The nesting level of a stored procedure, function, or view exceeds 32.</span></span>  
  
     <span data-ttu-id="832ec-200">SqlMetal이 이 예외를 catch하여 경고로 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-200">SqlMetal catches this exception and reports it as a warning.</span></span>  
  
 <span data-ttu-id="832ec-201">입력 파일 이름을 지정하려면 이름을 명령줄에 입력 파일로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-201">To specify an input file name, add the name to the command line as the input file.</span></span> <span data-ttu-id="832ec-202">**/conn** 옵션을 사용하여 연결 문자열에 파일 이름을 포함할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-202">Including the file name in the connection string (using the **/conn** option) is not supported.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="832ec-203">예제</span><span class="sxs-lookup"><span data-stu-id="832ec-203">Examples</span></span>  
 <span data-ttu-id="832ec-204">추출된 SQL 메타데이터를 포함하는 .dbml 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-204">Generate a .dbml file that includes extracted SQL metadata:</span></span>  
  
 <span data-ttu-id="832ec-205">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span><span class="sxs-lookup"><span data-stu-id="832ec-205">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span></span>  
  
 <span data-ttu-id="832ec-206">SQL Server Express를 사용하여 .mdf 파일에서 추출한 SQL 메타데이터를 포함하는 .dbml 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-206">Generate a .dbml file that includes extracted SQL metadata from an .mdf file by using SQL Server Express:</span></span>  
  
 <span data-ttu-id="832ec-207">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span><span class="sxs-lookup"><span data-stu-id="832ec-207">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span></span>  
  
 <span data-ttu-id="832ec-208">SQL Server Express에서 추출한 SQL 메타데이터를 포함하는 .dbml 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-208">Generate a .dbml file that includes extracted SQL metadata from SQL Server Express:</span></span>  
  
 <span data-ttu-id="832ec-209">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span><span class="sxs-lookup"><span data-stu-id="832ec-209">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span></span>  
  
 <span data-ttu-id="832ec-210">.dbml 메타데이터 파일에서 소스 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-210">Generate source code from a .dbml metadata file:</span></span>  
  
 <span data-ttu-id="832ec-211">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span><span class="sxs-lookup"><span data-stu-id="832ec-211">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span></span>  
  
 <span data-ttu-id="832ec-212">SQL 메타데이터에서 직접 소스 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-212">Generate source code from SQL metadata directly:</span></span>  
  
 <span data-ttu-id="832ec-213">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span><span class="sxs-lookup"><span data-stu-id="832ec-213">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="832ec-214">Northwind 샘플 데이터베이스에 **/pluralize** 옵션을 사용하는 경우에는 다음 동작에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="832ec-214">When you use the **/pluralize** option with the Northwind sample database, note the following behavior.</span></span> <span data-ttu-id="832ec-215">SqlMetal이 테이블에 대해 행 형식 이름을 만들면 테이블 이름은 단수가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-215">When SqlMetal makes row-type names for tables, the table names are singular.</span></span> <span data-ttu-id="832ec-216">그리고 테이블에 대해 <xref:System.Data.Linq.DataContext> 속성을 만드는 경우에는 테이블 이름이 복수가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-216">When it makes <xref:System.Data.Linq.DataContext> properties for tables, the table names are plural.</span></span> <span data-ttu-id="832ec-217">이와 동시에 Northwind 샘플 데이터베이스의 테이블은 미리 복수로 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-217">Coincidentally, the tables in the Northwind sample database are already plural.</span></span> <span data-ttu-id="832ec-218">그러므로 이러한 작업이 실제로 수행되는지 확인할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-218">Therefore, you do not see that part working.</span></span> <span data-ttu-id="832ec-219">일반적으로는 데이터베이스 테이블 이름을 단수로 지정하지만 .NET에서는 컬렉션 이름을 복수로 지정하는 경우도 많습니다.</span><span class="sxs-lookup"><span data-stu-id="832ec-219">Although it is common practice to name database tables singular, it is also a common practice in .NET to name collections plural.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="832ec-220">참고 항목</span><span class="sxs-lookup"><span data-stu-id="832ec-220">See Also</span></span>  
 [<span data-ttu-id="832ec-221">방법: Visual Basic 또는 C#에서 개체 모델 생성</span><span class="sxs-lookup"><span data-stu-id="832ec-221">How to: Generate the Object Model in Visual Basic or C#</span></span>](../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)  
 [<span data-ttu-id="832ec-222">LINQ to SQL에서 코드 생성</span><span class="sxs-lookup"><span data-stu-id="832ec-222">Code Generation in LINQ to SQL</span></span>](../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  
 [<span data-ttu-id="832ec-223">외부 매핑</span><span class="sxs-lookup"><span data-stu-id="832ec-223">External Mapping</span></span>](../../../docs/framework/data/adonet/sql/linq/external-mapping.md)
