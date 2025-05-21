# Front Banners

This repository is used as storage for banners images and management. 

It is composed of 2 parts : images and xmls. 

## Concerning XMLs

There is 2 XMLs, one for the french version and one for the english version.

### XML Structure: `BannersList`

This document describes the structure of an XML file used to define a list of banners to be displayed, for example on a website or application.

#### Example

```xml
<BannersList>
    <Banner>
        <URL>https://example.com/image1.png</URL>
        <StartDate>2024-11-30</StartDate>
        <EndDate>2029-11-30</EndDate>
        <RedirectURL>https://example.com/page1</RedirectURL>
        <Priority>0</Priority>
    </Banner>
    <Banner>
        ...
    </Banner>
</BannersList>
```

#### Root Element

- `<BannersList>` is the root element.
- It contains one or more `<Banner>` elements.

#### `<Banner>` Fields

Each `<Banner>` element must include the following fields:

| Field         | Type    | Format       | Description                                                  |
|---------------|---------|--------------|--------------------------------------------------------------|
| `URL`         | string  | URL          | Link to the image to display in the banner.                 |
| `StartDate`   | string  | `YYYY-MM-DD` | Start date of the banner's display period.                  |
| `EndDate`     | string  | `YYYY-MM-DD` | End date of the banner's display period.                    |
| `RedirectURL` | string  | URL          | Target URL when the banner is clicked.                      |
| `Priority`    | integer | `0`, `1`, …  | Display priority (lower number = higher priority).          |

#### Constraints

- All fields are **required**.
- Dates must follow the `YYYY-MM-DD` format (ISO 8601).
- URLs must be valid and accessible.
- `Priority` should be a non-negative integer. Lower values indicate higher priority.

#### Notes

- This XML can be used for dynamically displaying banners based on time range and priority.
- It can be parsed by a frontend or backend system to render and manage banners automatically.

## Concerning Images

These are the images displayed in the banner and used in the <URL> field in the XML as seen above. 
The link must be the raw version of the picture, which can be accessed by adding `?raw=true` at the end of the file URL. 

For optimal display, the picture should be a png with landscape orientation and a 470x205px size.
