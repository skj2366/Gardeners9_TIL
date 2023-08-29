### Laravel aws-sdk 

###### 파일 크기 가져오기
```php
 $s3Client = new S3Client([
                'credentials' => [
                    'key'    => 'aws key',
                    'secret' => 'aws secret'
                ],
                'region'      => 'region',
                'version'     => 'version',
                'use_path_style_endpoint' => true,
                'endpoint'    => 'endpoint'
            ]);

// 파일 크기 가져오기
$result = $s3Client->headObject([
    'Bucket' => $bucket,
    'Key'    => $filename
]);
$fileSize = $result['ContentLength'];
```

###### Make Presigned URL

``` php 
public function getPreSignedUrl()
{
        $command = $this->getClient()->getCommand(
            'GetObject',
            [
                'Bucket' => 'bucketname',
                'Key' => 'key',
            ]
        );
        $request = $this->getClient()->createPresignedRequest($command, '+120 minutes');
        $preSignedUrl = (string)$request->getUri();

        return $preSignedUrl;
}
```

