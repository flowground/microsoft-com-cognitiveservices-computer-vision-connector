# ![LOGO](logo.png) Computer Vision Client **flow**ground Connector

## Description

A generated **flow**ground connector for the Computer Vision Client API (version 2.0).

Generated from: https://api.apis.guru/v2/specs/microsoft.com/cognitiveservices-ComputerVision/2.0/swagger.json<br/>
Generated at: 2019-05-07T17:43:00+03:00

## API Description

The Computer Vision API provides state-of-the-art algorithms to process images and return information. For example, it can be used to determine if an image contains mature content, or it can be used to find all the faces in an image.  It also has other features like estimating dominant and accent colors, categorizing the content of images, and describing an image with complete English sentences.  Additionally, it can also intelligently generate images thumbnails for displaying large images effectively.

## Authorization

Supported authorization schemes:
- API Key
## Actions

### This operation extracts a rich set of visual features based on the image content.<br/>
> Two input methods are supported -- (1) Uploading an image or (2) specifying an image URL. Within your request, there is an optional parameter to allow you to choose which features to return. By default, image categories are returned in the response.<br/>
> A successful response will be returned in JSON. If the request failed, the response will contain an error code and a message to help understand what went wrong.

#### Input Parameters
* `visualFeatures` - _optional_ - A string indicating what visual feature types to return. Multiple values should be comma-separated. Valid visual feature types include: Categories - categorizes image content according to a taxonomy defined in documentation. Tags - tags the image with a detailed list of words related to the image content. Description - describes the image content with a complete English sentence. Faces - detects if faces are present. If present, generate coordinates, gender and age. ImageType - detects if image is clipart or a line drawing. Color - determines the accent color, dominant color, and whether an image is black&white. Adult - detects if the image is pornographic in nature (depicts nudity or a sex act).  Sexually suggestive content is also detected. Objects - detects various objects within an image, including the approximate location. The Objects argument is only available in English. Brands - detects various brands within an image, including the approximate location. The Brands argument is only available in English.
* `details` - _optional_ - A string indicating which domain-specific details to return. Multiple values should be comma-separated. Valid visual feature types include: Celebrities - identifies celebrities if detected in the image, Landmarks - identifies notable landmarks in the image.
* `language` - _optional_ - The desired language for output generation. If this parameter is not specified, the default value is &quot;en&quot;.Supported languages:en - English, Default. es - Spanish, ja - Japanese, pt - Portuguese, zh - Simplified Chinese.
    Possible values: en, es, ja, pt, zh.

### This operation returns a bounding box around the most important area of the image.<br/>
> A successful response will be returned in JSON. If the request failed, the response contains an error code and a message to help determine what went wrong.<br/>
> Upon failure, the error code and an error message are returned. The error code could be one of InvalidImageUrl, InvalidImageFormat, InvalidImageSize, NotSupportedImage, FailedToProcess, Timeout, or InternalServerError.

### This operation generates a description of an image in human readable language with complete sentences. The description is based on a collection of content tags, which are also returned by the operation. More than one description can be generated for each image. Descriptions are ordered by their confidence score. All descriptions are in English.<br/>
> Two input methods are supported -- (1) Uploading an image or (2) specifying an image URL.<br/>
> A successful response will be returned in JSON. If the request failed, the response will contain an error code and a message to help understand what went wrong.

#### Input Parameters
* `maxCandidates` - _optional_ - Maximum number of candidate descriptions to be returned.  The default is 1.
* `language` - _optional_ - The desired language for output generation. If this parameter is not specified, the default value is &quot;en&quot;.Supported languages:en - English, Default. es - Spanish, ja - Japanese, pt - Portuguese, zh - Simplified Chinese.
    Possible values: en, es, ja, pt, zh.

### Performs object detection on the specified image.<br/>
> Two input methods are supported -- (1) Uploading an image or (2) specifying an image URL.<br/>
> A successful response will be returned in JSON. If the request failed, the response will contain an error code and a message to help understand what went wrong.

### This operation generates a thumbnail image with the user-specified width and height. By default, the service analyzes the image, identifies the region of interest (ROI), and generates smart cropping coordinates based on the ROI. Smart cropping helps when you specify an aspect ratio that differs from that of the input image.<br/>
> A successful response contains the thumbnail image binary. If the request failed, the response contains an error code and a message to help determine what went wrong.<br/>
> Upon failure, the error code and an error message are returned. The error code could be one of InvalidImageUrl, InvalidImageFormat, InvalidImageSize, InvalidThumbnailSize, NotSupportedImage, FailedToProcess, Timeout, or InternalServerError.

#### Input Parameters
* `width` - _required_ - Width of the thumbnail, in pixels. It must be between 1 and 1024. Recommended minimum of 50.
* `height` - _required_ - Height of the thumbnail, in pixels. It must be between 1 and 1024. Recommended minimum of 50.
* `smartCropping` - _optional_ - Boolean flag for enabling smart cropping.

### This operation returns the list of domain-specific models that are supported by the Computer Vision API. Currently, the API supports following domain-specific models: celebrity recognizer, landmark recognizer.<br/>
> A successful response will be returned in JSON. If the request failed, the response will contain an error code and a message to help understand what went wrong.

### This operation recognizes content within an image by applying a domain-specific model. The list of domain-specific models that are supported by the Computer Vision API can be retrieved using the /models GET request. Currently, the API provides following domain-specific models: celebrities, landmarks.<br/>
> Two input methods are supported -- (1) Uploading an image or (2) specifying an image URL.<br/>
> A successful response will be returned in JSON.<br/>
> If the request failed, the response will contain an error code and a message to help understand what went wrong.

#### Input Parameters
* `model` - _required_ - The domain-specific content to recognize.
* `language` - _optional_ - The desired language for output generation. If this parameter is not specified, the default value is &quot;en&quot;.Supported languages:en - English, Default. es - Spanish, ja - Japanese, pt - Portuguese, zh - Simplified Chinese.
    Possible values: en, es, ja, pt, zh.

### Optical Character Recognition (OCR) detects text in an image and extracts the recognized characters into a machine-usable character stream.<br/>
> Upon success, the OCR results will be returned.<br/>
> Upon failure, the error code together with an error message will be returned. The error code can be one of InvalidImageUrl, InvalidImageFormat, InvalidImageSize, NotSupportedImage, NotSupportedLanguage, or InternalServerError.

#### Input Parameters
* `detectOrientation` - _required_ - Whether detect the text orientation in the image. With detectOrientation=true the OCR service tries to detect the image orientation and correct it before further processing (e.g. if it's upside-down).
* `language` - _optional_ - The BCP-47 language code of the text to be detected in the image. The default value is 'unk'.
    Possible values: unk, zh-Hans, zh-Hant, cs, da, nl, en, fi, fr, de, el, hu, it, ja, ko, nb, pl, pt, ru, es, sv, tr, ar, ro, sr-Cyrl, sr-Latn, sk.

### This operation generates a list of words, or tags, that are relevant to the content of the supplied image. The Computer Vision API can return tags based on objects, living beings, scenery or actions found in images. Unlike categories, tags are not organized according to a hierarchical classification system, but correspond to image content. Tags may contain hints to avoid ambiguity or provide context, for example the tag "cello" may be accompanied by the hint "musical instrument". All tags are in English.<br/>
> Two input methods are supported -- (1) Uploading an image or (2) specifying an image URL.<br/>
> A successful response will be returned in JSON. If the request failed, the response will contain an error code and a message to help understand what went wrong.

#### Input Parameters
* `language` - _optional_ - The desired language for output generation. If this parameter is not specified, the default value is &quot;en&quot;.Supported languages:en - English, Default. es - Spanish, ja - Japanese, pt - Portuguese, zh - Simplified Chinese.
    Possible values: en, es, ja, pt, zh.

## License

**flow**ground :- Telekom iPaaS / microsoft-com-cognitiveservices-computer-vision-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
