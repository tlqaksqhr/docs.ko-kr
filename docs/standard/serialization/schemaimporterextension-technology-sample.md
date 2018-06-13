---
title: SchemaImporterExtension 기술 샘플
ms.date: 03/30/2017
ms.assetid: 3f5eb78f-0ef6-433a-b095-3a63b1ce0bc9
ms.openlocfilehash: 07856c9825785aa7bbc123d0a835e4dc863b8ec6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33581357"
---
# <a name="schemaimporterextension-technology-sample"></a><span data-ttu-id="0542d-102">SchemaImporterExtension 기술 샘플</span><span class="sxs-lookup"><span data-stu-id="0542d-102">SchemaImporterExtension Technology Sample</span></span>
[<span data-ttu-id="0542d-103">샘플 다운로드</span><span class="sxs-lookup"><span data-stu-id="0542d-103">Download Sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/SchemaImporterExtension.zip.exe)  
  
 <span data-ttu-id="0542d-104">이 샘플에서는 XML 스키마를 가져올 때의 코드 생성을 자세히 제어할 수 있는 사용자 지정 <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension>을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0542d-104">This sample demonstrates a custom <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> that allows fine control over code generation when an XML schema is imported.</span></span> <span data-ttu-id="0542d-105">이 응용 프로그램에서는 이러한 확장을 빌드, 등록 및 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0542d-105">The application shows how to build, register and invoke this extension.</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="0542d-106">명령 프롬프트를 사용하여 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="0542d-106">To build the sample using the command prompt</span></span>  
  
1.  <span data-ttu-id="0542d-107">명령 프롬프트 창을 열고 샘플에 대한 언어별 하위 디렉터리 중 하나로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0542d-107">Open a Command Prompt window and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="0542d-108">명령줄에 **msbuild.exe OrderSchemaImporterExtension.sln**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0542d-108">Type **msbuild.exe OrderSchemaImporterExtension.sln** at the command line.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="0542d-109">Visual Studio를 사용하여 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="0542d-109">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="0542d-110">[!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)]를 열고 샘플에 대한 언어별 하위 디렉터리 중 하나로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0542d-110">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="0542d-111">OrderSchemaImporterExtension.sln의 아이콘을 두 번 클릭하여 Visual Studio에서 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0542d-111">Double-click the icon for OrderSchemaImporterExtension.sln to open the file in Visual Studio.</span></span>  
  
3.  <span data-ttu-id="0542d-112">**빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0542d-112">On the **Build** menu, click **Build Solution**.</span></span>  
  
 <span data-ttu-id="0542d-113">응용 프로그램이 기본 \bin 또는 \bin\Debug 디렉터리에 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="0542d-113">The application will be built in the default \bin or \bin\Debug directory.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="0542d-114">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="0542d-114">To run the sample</span></span>  
  
1.  <span data-ttu-id="0542d-115">명령 프롬프트를 사용하여 새 실행 파일이 있는 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0542d-115">Navigate to the directory containing the new executable, using the command prompt.</span></span>  
  
2.  <span data-ttu-id="0542d-116">명령줄에 **[exe name]** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0542d-116">Type **[exe name]** at the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0542d-117">설명</span><span class="sxs-lookup"><span data-stu-id="0542d-117">Remarks</span></span>  
 <span data-ttu-id="0542d-118">샘플의 이진 생성 및 등록 단계에 대한 자세한 내용은 소스 코드의 주석 및 build.proj 파일을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0542d-118">For more information about sample binary creation and registration steps, see the comments in the source code and build.proj files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0542d-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0542d-119">See Also</span></span>  
 <xref:System.CodeDom.CodeCompileUnit>  
 <xref:System.CodeDom.CodeNamespace>  
 <xref:System.CodeDom.CodeNamespaceImport>  
 <xref:Microsoft.CSharp.CSharpCodeProvider>  
 <xref:System.Xml.Serialization.IXmlSerializable>  
 <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension>  
 <xref:System.CodeDom>  
 <xref:System.CodeDom.Compiler>  
 <xref:System.Web.Services.Description>  
 <xref:System.Web.Services.Discovery>  
 <xref:System.Xml.Serialization>  
 <xref:System.Uri>  
 <xref:Microsoft.VisualBasic.VBCodeProvider>  
 <xref:System.Web.Services.Description.WebReference>  
 <xref:System.Xml.Serialization.XmlSchemaImporter>
