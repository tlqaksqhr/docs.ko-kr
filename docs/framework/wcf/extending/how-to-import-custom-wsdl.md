---
title: "방법: 사용자 지정 WSDL 가져오기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ddc3718d-ce60-44f6-92af-a5c67477dd99
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 00a845fe5c8321d521fb7baa3b16bd009fc3e660
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-import-custom-wsdl"></a>방법: 사용자 지정 WSDL 가져오기
이 항목에서는 사용자 지정 WSDL을 가져오는 방법에 대해 설명합니다. 사용자 지정 WSDL을 처리하려면 <xref:System.ServiceModel.Description.IWsdlImportExtension> 인터페이스를 구현해야 합니다.  
  
### <a name="to-import-custom-wsdl"></a>사용자 지정 WSDL을 가져오려면  
  
1.  <xref:System.ServiceModel.Description.IWsdlImportExtension>를 구현해야 합니다. <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29> 메서드를 구현하여 메타데이터를 가져오기 전에 수정합니다. <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> 및 <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> 메서드를 구현하여 메타데이터에서 가져온 계약과 끝점을 수정합니다. 가져온 계약이나 끝점에 액세스하려면 해당 컨텍스트 개체(<xref:System.ServiceModel.Description.WsdlContractConversionContext> 또는 <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>)를 사용합니다.  
  
    ```  
    public class WsdlDocumentationImporter : IWsdlImportExtension  
       {  
          public void ImportContract(WsdlImporter importer, WsdlContractConversionContext context)  
    {  
            // Contract documentation  
         if (context.WsdlPortType.Documentation != null)  
         {  
               context.Contract.Behaviors.Add(new WsdlDocumentationImporter(context.WsdlPortType.Documentation));  
    }  
    // Operation documentation  
    foreach (Operation operation in context.WsdlPortType.Operations)  
    {  
    if (operation.Documentation != null)  
    {  
    OperationDescription operationDescription = context.Contract.Operations.Find(operation.Name);  
    if (operationDescription != null)  
    {  
                            operationDescription.Behaviors.Add(new WsdlDocumentationImporter(operation.Documentation));  
    }  
    }  
    }  
    }  
  
    public void BeforeImport(ServiceDescriptionCollection wsdlDocuments, XmlSchemaSet xmlSchemas, ICollection<XmlElement> policy)   
            {  
                Console.WriteLine("BeforeImport called.");  
            }  
  
    public void ImportEndpoint(WsdlImporter importer, WsdlEndpointConversionContext context)   
            {  
                Console.WriteLine("ImportEndpoint called.");  
            }  
       }  
    ```  
  
2.  사용자 지정 WSDL 가져오기를 사용하도록 클라이언트 응용 프로그램을 구성합니다. Svcutil.exe를 사용하는 경우 Svcutil.exe(Svcutil.exe.config)의 구성 파일에 이 구성을 추가해야 합니다.  
  
    ```xml  
    <system.serviceModel>  
          <client>  
            <endpoint   
              address="http://localhost:8000/Fibonacci"   
              binding="wsHttpBinding"  
              contract="IFibonacci"  
            />  
            <metadata>  
              <wsdlImporters>  
                <extension type="Microsoft.WCF.Documentation.WsdlDocumentationImporter, WsdlDocumentation" />  
              </wsdlImporters>  
            </metadata>  
          </client>  
        </system.serviceModel>  
    ```  
  
3.  새 <xref:System.ServiceModel.Description.WsdlImporter> 인스턴스(가져올 WSDL 문서를 포함하는 <xref:System.ServiceModel.Description.MetadataSet> 인스턴스에 전달)를 만들고 <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>를 호출합니다.  
  
    ```  
    WsdlImporter importer = new WsdlImporter(metaDocs);          System.Collections.ObjectModel.Collection<ContractDescription> contracts  = importer.ImportAllContracts();  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [메타 데이터](../../../../docs/framework/wcf/feature-details/metadata.md)  
 [내보내기 및 메타 데이터 가져오기](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)  
 [사용자 지정 WSDL 게시](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md)
