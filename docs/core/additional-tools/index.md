---
title: .NET Core 추가 도구
description: .NET Core 기능을 지원하고 확장하는 추가 도구에 대한 개요입니다.
author: mlacouture
ms.author: johalex
ms.date: 01/19/2018
ms.custom: mvc
ms.openlocfilehash: 578d42e5a0a11ae76410289142d47c8d65abe7aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="net-core-additional-tools"></a><span data-ttu-id="cf8aa-103">.NET Core 추가 도구</span><span class="sxs-lookup"><span data-stu-id="cf8aa-103">.NET Core additional tools</span></span>

<span data-ttu-id="cf8aa-104">이 섹션에서는 [.NET Core CLI (명령줄 인터페이스)](..\tools\index.md) 도구 외에 .NET Core 기능을 지원하고 확장하는 도구 목록을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8aa-104">This section compiles a list of tools that support and extend the .NET Core functionality, in addition to the [.NET Core command-line interface (CLI)](..\tools\index.md) tools.</span></span>

## <a name="wcf-web-service-reference-toolwcf-web-service-reference-guidemd"></a>[<span data-ttu-id="cf8aa-105">WCF Web Service Reference Tool</span><span class="sxs-lookup"><span data-stu-id="cf8aa-105">WCF Web Service Reference Tool</span></span>](wcf-web-service-reference-guide.md)

<span data-ttu-id="cf8aa-106">WCF Web Service Reference는 [Visual Studio 2017 버전 15.5](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes#WCFTools)에서 처음 공개된 Visual Studio 연결된 서비스 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="cf8aa-106">The WCF Web Service Reference is a Visual Studio connected service provider that made its debut in [Visual Studio 2017 version 15.5](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes#WCFTools).</span></span> <span data-ttu-id="cf8aa-107">이 도구는 현재 솔루션, 네트워크 위치 또는 WSDL 파일의 웹 서비스에서 메타 데이터를 검색하고, 해당 웹 서비스를 액세스하는 데 사용할 수 있는 WCF(Windows Communication Foundation) 클라이언트 프록시 코드가 포함된 .NET Core 호환 소스 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8aa-107">This tool retrieves metadata from a web service in the current solution, on a network location, or from a WSDL file, and generates a .NET Core compatible source file containing Windows Communication Foundation (WCF) client proxy code that you can use to access the web service.</span></span>

## <a name="xml-serializer-generatorxml-serializer-generatormd"></a>[<span data-ttu-id="cf8aa-108">XML Serializer Generator</span><span class="sxs-lookup"><span data-stu-id="cf8aa-108">XML Serializer Generator</span></span>](xml-serializer-generator.md)

<span data-ttu-id="cf8aa-109">.NET Framework용 [Xml Serializer Generator(sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md)와 마찬가지로, [Microsoft.XmlSerializer.Generator NuGet 패키지](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator)는 .NET Core 및 .NET Standard 라이브러리용 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="cf8aa-109">Like the [Xml Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) for the .NET Framework, the [Microsoft.XmlSerializer.Generator NuGet package](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) is the solution for .NET Core and .NET Standard libraries.</span></span> <span data-ttu-id="cf8aa-110"><xref:System.Xml.Serialization.XmlSerializer>를 사용하여 해당 형식의 개체를 직렬화하거나 역직렬화할 때 XML serialization의 시작 성능을 향상시키기 위해 어셈블리에 포함된 형식의 XML serialization 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf8aa-110">It creates an XML serialization assembly for types contained in an assembly to improve the startup performance of XML serialization when serializing or de-serializing objects of those types using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>