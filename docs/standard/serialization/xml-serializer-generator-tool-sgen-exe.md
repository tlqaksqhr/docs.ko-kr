---
title: "XML Serializer 생성기 도구(Sgen.exe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc1d1f1c-fb26-4be9-885a-3fe84c81cec6
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 41f71519ee8945ae93b85e7f6ac2725bf50d4913
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="xml-serializer-generator-tool-sgenexe"></a><span data-ttu-id="e7528-102">XML Serializer 생성기 도구(Sgen.exe)</span><span class="sxs-lookup"><span data-stu-id="e7528-102">XML Serializer Generator Tool (Sgen.exe)</span></span>
<span data-ttu-id="e7528-103">XML Serializer 생성기에서 지정된 어셈블리의 형식에 대해 XML serialization 어셈블리를 만들면 지정된 형식의 개체를 serialize 또는 deserialize할 때 <xref:System.Xml.Serialization.XmlSerializer>의 시작 성능을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-103">The XML Serializer Generator creates an XML serialization assembly for types in a specified assembly in order to improve the startup performance of a <xref:System.Xml.Serialization.XmlSerializer> when it serializes or deserializes objects of the specified types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7528-104">구문</span><span class="sxs-lookup"><span data-stu-id="e7528-104">Syntax</span></span>  
  
```  
sgen [options]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e7528-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e7528-105">Parameters</span></span>  
  
|<span data-ttu-id="e7528-106">옵션</span><span class="sxs-lookup"><span data-stu-id="e7528-106">Option</span></span>|<span data-ttu-id="e7528-107">설명</span><span class="sxs-lookup"><span data-stu-id="e7528-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e7528-108">**/a**[**ssembly**]**:***filename*</span><span class="sxs-lookup"><span data-stu-id="e7528-108">**/a**[**ssembly**]**:***filename*</span></span>|<span data-ttu-id="e7528-109">*filename*에서 지정한 어셈블리 또는 실행 파일에 있는 모든 형식에 대해 serialization 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-109">Generates serialization code for all the types contained in the assembly or executable specified by *filename*.</span></span> <span data-ttu-id="e7528-110">파일 이름은 하나만 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-110">Only one file name can be provided.</span></span> <span data-ttu-id="e7528-111">이 인수가 반복되면 마지막 파일 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-111">If this argument is repeated, the last file name is used.</span></span>|  
|<span data-ttu-id="e7528-112">**/c[ompiler]:** *options*</span><span class="sxs-lookup"><span data-stu-id="e7528-112">**/c[ompiler]:** *options*</span></span>|<span data-ttu-id="e7528-113">C# 컴파일러로 전달될 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-113">Specifies the options to pass to the C# compiler.</span></span> <span data-ttu-id="e7528-114">모든 csc.exe 옵션이 컴파일러로 전달되어 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-114">All csc.exe options are supported as they are passed to the compiler.</span></span> <span data-ttu-id="e7528-115">이 옵션은 어셈블리에서 서명되도록 지정할 때와 키 파일을 지정할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-115">This can be used to specify that the assembly should be signed and to specify the key file.</span></span>|  
|<span data-ttu-id="e7528-116">**/d**[**ebug**]</span><span class="sxs-lookup"><span data-stu-id="e7528-116">**/d**[**ebug**]</span></span>|<span data-ttu-id="e7528-117">디버거에서 사용할 수 있는 이미지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-117">Generates an image that can be used with a debugger.</span></span>|  
|<span data-ttu-id="e7528-118">**/f[orce]**</span><span class="sxs-lookup"><span data-stu-id="e7528-118">**/f[orce]**</span></span>|<span data-ttu-id="e7528-119">이름이 같은 기존 어셈블리를 덮어쓰게 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-119">Forces the overwriting of an existing assembly of the same name.</span></span> <span data-ttu-id="e7528-120">기본값은 **false**입니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-120">The default is **false**.</span></span>|  
|<span data-ttu-id="e7528-121">**/help 또는 /?**</span><span class="sxs-lookup"><span data-stu-id="e7528-121">**/help or /?**</span></span>|<span data-ttu-id="e7528-122">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-122">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="e7528-123">**/k**[**eep**]</span><span class="sxs-lookup"><span data-stu-id="e7528-123">**/k**[**eep**]</span></span>|<span data-ttu-id="e7528-124">생성된 소스 파일 및 기타 임시 파일이 serialization 어셈블리로 컴파일된 후에는 이 파일을 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-124">Suppresses the deletion of the generated source files and other temporary files after they have been compiled into the serialization assembly.</span></span> <span data-ttu-id="e7528-125">이 도구에서 특정 형식에 대해 serialization 코드를 생성하는지 여부를 확인하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-125">This can be used to determine whether the tool is generating serialization code for a particular type.</span></span>|  
|<span data-ttu-id="e7528-126">**/n**[**ologo**]</span><span class="sxs-lookup"><span data-stu-id="e7528-126">**/n**[**ologo**]</span></span>|<span data-ttu-id="e7528-127">Microsoft 시작 배너를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-127">Suppresses the display of the Microsoft startup banner.</span></span>|  
|<span data-ttu-id="e7528-128">**/o**[**ut**]**:***path*</span><span class="sxs-lookup"><span data-stu-id="e7528-128">**/o**[**ut**]**:***path*</span></span>|<span data-ttu-id="e7528-129">생성된 어셈블리를 저장할 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-129">Specifies the directory in which to save the generated assembly.</span></span> <span data-ttu-id="e7528-130">**참고:** 생성된 어셈블리의 이름은 입력 어셈블리의 이름과 “xmlSerializers.dll”로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-130">**Note:**  The name of the generated assembly is composed of the name of the input assembly plus "xmlSerializers.dll".</span></span>|  
|<span data-ttu-id="e7528-131">**/p**[**roxytypes**]</span><span class="sxs-lookup"><span data-stu-id="e7528-131">**/p**[**roxytypes**]</span></span>|<span data-ttu-id="e7528-132">XML Web services 프록시 형식에 대해서만 serialization 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-132">Generates serialization code only for the XML Web service proxy types.</span></span>|  
|<span data-ttu-id="e7528-133">**/r**[**eference**]**:***assemblyfiles*</span><span class="sxs-lookup"><span data-stu-id="e7528-133">**/r**[**eference**]**:***assemblyfiles*</span></span>|<span data-ttu-id="e7528-134">XML serialization이 필요한 형식에서 참조하는 어셈블리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-134">Specifies the assemblies that are referenced by the types requiring XML serialization.</span></span> <span data-ttu-id="e7528-135">여러 개의 어셈블리 파일을 쉼표로 구분할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-135">Accepts multiple assembly files separated by commas.</span></span>|  
|<span data-ttu-id="e7528-136">**/s**[**ilent**]</span><span class="sxs-lookup"><span data-stu-id="e7528-136">**/s**[**ilent**]</span></span>|<span data-ttu-id="e7528-137">성공 메시지를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-137">Suppresses the display of success messages.</span></span>|  
|<span data-ttu-id="e7528-138">**/t**[**ype**]**:***type*</span><span class="sxs-lookup"><span data-stu-id="e7528-138">**/t**[**ype**]**:***type*</span></span>|<span data-ttu-id="e7528-139">지정된 형식에 대해서만 serialization 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-139">Generates serialization code only for the specified type.</span></span>|  
|<span data-ttu-id="e7528-140">**/v**[**erbose**]</span><span class="sxs-lookup"><span data-stu-id="e7528-140">**/v**[**erbose**]</span></span>|<span data-ttu-id="e7528-141">디버깅에 대한 자세한 출력을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-141">Displays verbose output for debugging.</span></span> <span data-ttu-id="e7528-142">대상 어셈블리에서 <xref:System.Xml.Serialization.XmlSerializer>로 serialize할 수 없는 형식을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-142">Lists types from the target assembly that cannot be serialized with the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|<span data-ttu-id="e7528-143">**/?**</span><span class="sxs-lookup"><span data-stu-id="e7528-143">**/?**</span></span>|<span data-ttu-id="e7528-144">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-144">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7528-145">설명</span><span class="sxs-lookup"><span data-stu-id="e7528-145">Remarks</span></span>  
 <span data-ttu-id="e7528-146">XML Serializer 생성기를 사용하지 않을 경우, <xref:System.Xml.Serialization.XmlSerializer>는 응용 프로그램이 실행될 때마다 각 형식에 대해 serialization 코드 및 serialization 어셈블리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-146">When the XML Serializer Generator is not used, a <xref:System.Xml.Serialization.XmlSerializer> generates serialization code and a serialization assembly for each type every time an application is run.</span></span> <span data-ttu-id="e7528-147">XML serialization 시작 성능을 높이려면 Sgen.exe 도구를 사용하여 미리 어셈블리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-147">To improve the performance of XML serialization startup, use the Sgen.exe tool to generate those assemblies the assemblies in advance.</span></span> <span data-ttu-id="e7528-148">그런 다음 응용 프로그램과 함께 이 어셈블리를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-148">These assemblies can then be deployed with the application.</span></span>  
  
 <span data-ttu-id="e7528-149">XML Serializer 생성기는 해당 형식이 맨 처음 로드될 때 serialization 프로세스에서 성능 손실을 유발하지 않으므로, 서버와의 통신에서 XML Web services 프록시를 사용하는 클라이언트의 성능도 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-149">The XML Serializer Generator can also improve the performance of clients that use XML Web service proxies to communicate with servers because the serialization process will not incur a performance hit when the type is loaded the first time.</span></span>  
  
 <span data-ttu-id="e7528-150">이렇게 생성된 어셈블리는 웹 서비스의 서버측에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-150">These generated assemblies cannot be used on the server side of a Web service.</span></span> <span data-ttu-id="e7528-151">이 도구는 웹 서비스 클라이언트 및 수동 serialization 시나리오에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-151">This tool is only for Web service clients and manual serialization scenarios.</span></span>  
  
 <span data-ttu-id="e7528-152">serialize할 형식을 포함하는 어셈블리의 이름이 MyType.dll이라면 연결된 serialization 어셈블리의 이름은 MyType.XmlSerializers.dll이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-152">If the assembly containing the type to serialize is named MyType.dll, then the associated serialization assembly will be named MyType.XmlSerializers.dll.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e7528-153">예제</span><span class="sxs-lookup"><span data-stu-id="e7528-153">Examples</span></span>  
 <span data-ttu-id="e7528-154">다음 명령에서는 Data.dll이라는 어셈블리에 포함된 모든 형식을 serialize하기 위해 Data.XmlSerializers.dll이라는 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-154">The following command creates an assembly named Data.XmlSerializers.dll for serializing all the types contained in the assembly named Data.dll.</span></span>  
  
```  
sgen Data.dll   
```  
  
 <span data-ttu-id="e7528-155">Data.XmlSerializers.dll 어셈블리는 Data.dll의 형식을 serialize/deserialize해야 하는 코드에서 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7528-155">The Data.XmlSerializers.dll assembly can be referenced from code that needs to serialize and deserialize the types in Data.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7528-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e7528-156">See Also</span></span>  
 [<span data-ttu-id="e7528-157">도구</span><span class="sxs-lookup"><span data-stu-id="e7528-157">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="e7528-158">XML 웹 서비스 개요</span><span class="sxs-lookup"><span data-stu-id="e7528-158">XML Web Services Overview</span></span>](http://msdn.microsoft.com/en-us/9db0c7b8-bca6-462b-9be5-f5f9a7f05a4d)  
 [<span data-ttu-id="e7528-159">명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="e7528-159">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
