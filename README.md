# myaf-image
myaf框架图形处理工具
## Demo
```
<?php

use \Myaf\Image\CoreImage;

class TestLImage
{
    private $file = __DIR__ . '/image/php.jpg';
    private $waterMarkFile = __DIR__ . '/image/ico.jpg';

    //下载验证码.
    public function downloadCaptcha()
    {
        CoreImage::downloadCaptcha('A3B2CD', 100, 32, 100);
    }

    //获取jpeg源数据.
    public function getCaptcha()
    {
        echo CoreImage::getCaptchaData('A33333', 100, 32, 100);
    }

    //保存验证码
    public function saveCaptcha()
    {
        $desFile = __DIR__ . '/image/save.jpeg';
        CoreImage::saveCaptcha('A44444', $desFile, 100, 32, 100);
    }

    //给图片加水印.
    public function waterMark()
    {
        $desFile = __DIR__ . '/image/new-water.jpeg';
        var_dump(CoreImage::waterMarkImage($this->file, $this->waterMarkFile, $desFile, 10, 10, 320, 220));
    }

    /**
     * 改变图片尺寸
     */
    public function resizeImage()
    {
        $desFile = __DIR__ . '/image/new-resize.jpeg';
        var_dump(CoreImage::resizeImage($this->file, 100, 100, $desFile));
    }

    /**
     * 旋转图片
     */
    public function rotateImage()
    {
        $desFile = __DIR__ . '/image/new-rotate.jpeg';
        var_dump(CoreImage::rotateImage($this->file, 90, $desFile));
    }

    public function image2Gif()
    {
        var_dump(CoreImage::image2Gif($this->file));
    }

    public function image2Png()
    {
        var_dump(CoreImage::image2Png($this->file));
    }
}

$image = new TestLImage();
//$image->saveCaptcha();
//$image->downloadCaptcha();
//$image->getCaptcha();
//$image->waterMark();
//$image->resizeImage();
//$image->rotateImage();
//$image->image2Gif();
$image->image2Png();
```