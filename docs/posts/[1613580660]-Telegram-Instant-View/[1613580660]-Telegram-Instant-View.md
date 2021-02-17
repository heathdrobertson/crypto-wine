![Cover Photo](../../assets/images/tetonblocks_blog_tetonblocks-post-cover.jpg)

# Telegram Instant View
**Wed-09:51AM 02-17-2021**

## TLDR


```bash
~version: "2.0"

?path: /tetonblocks-crypto/.+

#container-lg px-3 my-5 markdown-body
$main: //body

title: $main//h1[@id="-the-rough-draft"]
body: $main//div[has-class("markdown-body")]
author: "Heath Robertson"

@remove: $body//h1[has-class("tetonblocks-crypto-crew")]

---


~version: "2.0"

?path: /blog/.+
$main: //div[@id="dev_page_content_wrap"]

title:  $main//h1[1]
body:  //div[@id="dev_page_content"]
author: "Telegram"

cover: $main//*[has-class("blog_wide_image")]//img
cover: $main//img[has-class("blog_wide_image")]

image_url:   $cover/self::img/@src

$side_image: $main//img[has-class("blog_side_image")]
image_url:   $side_image/@src
@remove:     $side_image

<figcaption>: $body//div[has-class("blog_image_wrap")]/p
<figure>:     $body//div[has-class("blog_image_wrap")]
<figure>:     $body//div[has-class("blog_side_image_wrap")]
<figure>:     $body//div[has-class("smartphone_video_player_wrap")]


@remove: $body//*[has-class("twitter_timeline_wrap")]
@remove: $body/div/center[.//img]/br

$footer: $body/p[./em[contains(., "The Telegram Team")]]
@remove: $footer/prev-sibling::*[./br][not(normalize-space())]
@remove: $footer/next-sibling::*[./br][not(normalize-space())]
@remove: $footer



$related:  //div[has-class("tl_blog_bottom_blog")]
<h4>:      $related//a[has-class("side_blog_header")]
<related>: $related
@append_to($body)
```



---
## [TetonBlocks.io](https://tetonblocks.io)
### By: Heath Robertson


[Home](../../index.md) | [Twitter](https://twitter.com/TetonBlocks) | [Telegram](https://t.me/TetonPool)

![Footer Image](../../assets/images/tetonblocks_logo_banner.png)
