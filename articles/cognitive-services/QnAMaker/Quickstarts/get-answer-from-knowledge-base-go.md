---
title: "Quickstart: Get answer from knowledge base - REST, Go - QnA Maker"
description: This Go REST-based quickstart walks you through getting an answer from a knowledge base, programmatically.
ms.topic: quickstart
ms.date: 01/28/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.custom: RESTCHANGE-20200128
#Customer intent: As an API or REST developer new to the QnA Maker service, I want to programmatically get an answer a knowledge base using Go.
---

# Quickstart: Get answers to a question from a knowledge base with Go

This quickstart walks you through programmatically getting an answer from a published QnA Maker knowledge base. The knowledge base contains questions and answers from [data sources](../Concepts/knowledge-base.md) such as FAQs. The [question](../how-to/metadata-generateanswer-usage.md#generateanswer-request-configuration) is sent to the QnA Maker service. The [response](../how-to/metadata-generateanswer-usage.md#generateanswer-response-properties) includes the top-predicted answer.

[Reference documentation](https://docs.microsoft.com/rest/api/cognitiveservices/qnamakerruntime/runtime) | [Sample](https://github.com/Azure-Samples/cognitive-services-qnamaker-go/blob/master/documentation-samples/quickstarts/get-answer/get-answer.go)

## Prerequisites

* [Go 1.10.1](https://golang.org/dl/)
* [Visual Studio Code](https://code.visualstudio.com/)
* You must have a [QnA Maker service](../How-To/set-up-qnamaker-service-azure.md). To retrieve your key, select **Keys** under **Resource Management** in your Azure dashboard for your QnA Maker resource.
* **Publish** page settings. If you do not have a published knowledge base, create an empty knowledge base, then import a knowledge base on the **Settings** page, then publish. You can download and use [this basic knowledge base](https://github.com/Azure-Samples/cognitive-services-sample-data-files/blob/master/qna-maker/knowledge-bases/basic-kb.tsv).

    The publish page settings include POST route value, Host value, and EndpointKey value.

    ![Publish settings](../media/qnamaker-quickstart-get-answer/publish-settings.png)

## Create a Go file

Open VSCode and create a new file named `get-answer.go` and add the following class:

```Go
package main

func main() {

}
```

## Add the required dependencies

Above the `main` function, at the top of the `get-answer.go` file, add necessary dependencies to the project:

[!code-go[Add the required dependencies](~/samples-qnamaker-go/documentation-samples/quickstarts/get-answer/get-answer.go?range=3-9 "Add the required dependencies")]

## Add the required constants

At the top of the `main` function, add the required constants to access QnA Maker. These values are on the **Publish** page after you publish the knowledge base.

[!code-go[Add the required constants](~/samples-qnamaker-go/documentation-samples/quickstarts/get-answer/get-answer.go?range=17-33 "Add the required constants")]

## Add a POST request to send question and get answer

The following code makes an HTTPS request to the QnA Maker API to send the question to the knowledge base and receives the response:

[!code-go[Add a POST request to send question to knowledge base](~/samples-qnamaker-go/documentation-samples/quickstarts/get-answer/get-answer.go?range=35-48 "Add a POST request to send question to knowledge base")]

The `Authorization` header's value includes the string `EndpointKey`.

Learn more about the [request](../how-to/metadata-generateanswer-usage.md#generateanswer-request) and [response](../how-to/metadata-generateanswer-usage.md#generateanswer-response).

## Build and run the program

Build and run the program from the command line. It will automatically send the request to the QnA Maker API, then it will print to the console window.

1. Build the file:

    ```bash
    go build get-answer.go
    ```

1. Run the file:

    ```bash
    ./get-answer
    ```

[!INCLUDE [JSON request and response](../../../../includes/cognitive-services-qnamaker-quickstart-get-answer-json.md)]


[!INCLUDE [Clean up files and knowledge base](../../../../includes/cognitive-services-qnamaker-quickstart-cleanup-resources.md)]

## Next steps

> [!div class="nextstepaction"]
> [QnA Maker (V4) REST API Reference](https://go.microsoft.com/fwlink/?linkid=2092179)
