TurboRLE: Turbo Run Length Encoding [![Build Status](https://travis-ci.org/powturbo/TurboRLE.svg?branch=master)](https://travis-ci.org/powturbo/TurboRLE)
===================================

###### Efficient and fastest **Run Length Encoding** library
- 100% C (C++ compatible headers), without inline assembly
<p>
- Efficient compression 
- No other RLE compress or decompress faster with better compression
- :new: faster compression and 2x faster decompression with :+1: SIMD
- :new: **ZERO!** byte overhead
- Compress better and up to 8 times faster and decompress up to 4 times faster than other fast RLEs
  
<p>
- No modification of the raw data, preserving compressibility
- Order preserving 

###### TurboRLE
- **TRLE**: TurboRLE - Efficient and fast Run Length Encoding
<p>
- **SRLE**: TurboRLE Escape - Fast Run Length Encoding with automatic escape determination 

<p>
## Benchmark:
CPU: Sandy bridge i7-2600k at 4.2GHz, gcc 5.2, ubuntu 15.10
- with [TurboBench](https://github.com/powturbo/TurboBench)
- Single thread
- Realistic and practical benchmark with large files

###### Functions benchmarked
- **MRLE**: Mespotine RLE [MRLE](http://encode.ru/threads/2121-No-more-encoding-overhead-in-Run-Length-Encoding-Read-about-Mespotine-RLE-here-)
<p>
- **RLE64**: Run Length Encoding - [RLE64](http://sourceforge.net/projects/nikkhokkho/files/RLE64/)
<p>

- Text File: [enwik9bwt](http://mattmahoney.net/dc/textdata.html) enwik9 bwt generated w. [libdivsufsort](https://code.google.com/p/libdivsufsort/)

 (**bold** = pareto)  MB=1.000.000

|C Size|ratio%|C MB/s|D MB/s|Name|
|--------:|-----:|--------:|--------:|----------------|----------------|
|378458015| 37.8|**453.89**|**1908.41**|**trle**|
|419346351| 41.9|**595.40**|**4243.61**|**srle 8**|
|419346352| 41.9|484.17|4234.67|srle 0|
|422296235| 42.2|557.84|1364.10|**rle64 8**|
|487466207| 48.7|**1312.26**|4044.98|**srle 16**|
|498420792| 49.8|1113.81|2511.38|rle64 16|
|549218833| 54.9|**2541.74**|**6628.14**|**srle 32**|
|563503744| 56.4|**2730.54**|5073.81|**rle64 32**|
|576619945| 57.7|205.83|570.93|mrle|enwik9bwt|
|605766094| 60.6|**4678.70**|**7447.81**|**srle 64**|
|620676412| 62.1|**5247.28**|7376.44|**rle64 64**|
|1000000012|100.0|**8517.76**|**9176.59**|**memcpy**|

srle 0: RLE w/ auto escape
<p>
- Checkers program "End Game Table Base": [1034.db](http://encode.ru/threads/2077-EGTB-compression?p=41392&viewfull=1#post41392)

|C Size|ratio%|C MB/s|D MB/s|Name|
|--------:|-----:|--------:|--------:|----------------|----------------|
|82452164| 19.7|**652.87**|**3138.22**|**trle**|
|88055364| 21.0|233.07|1573.62|mrle|
|92539191| 22.1|**1116.08**|**5669.24**|**srle 8**|
|92539192| 22.1|778.72|5664.69|srle 0|
|93905327| 22.4|780.05|1659.48|rle64 8|
|113627625| 27.1|**1823.40**|5111.00|**srle 16**|
|117590491| 28.0|1341.02|2825.66|rle64 16|
|136924740| 32.7|**3135.97**|**7649.05**|**srle 32**|
|143953177| 34.3|2970.51|5506.36|rle64 32|
|165545036| 39.5|**5137.85**|**8081.30**|**srle 64**|
|176442237| 42.1|5090.87|7871.78|rle64 64|
|419225629|100.0|**8367.04**|**8934.25**|**memcpy**|

<p>
- BMP File: [girl.bmp in RLE64Samples](http://sourceforge.net/projects/nikkhokkho/files/RLE64/3.00/)

|C Size|ratio%|C MB/s|D MB/s|Name|
|--------:|-----:|--------:|--------:|----------------|----------------|
|3293899|  0.8|**1087.74**|**13113.37**|**trle**|
|4482388|  1.1|297.68|9209.99|mrle|
|4821162|  1.2|**9639.33**|13006.29|**srle 8**|
|4821163|  1.2|2051.44|13004.84|srle 0|
|8501660|  2.1|4398.45|10014.59|srle 16|
|8832647|  2.2|1274.23|2920.96|rle64 8|
|9265516|  2.3|2241.56|5721.46|rle64 16|
|13777939|  3.4|7312.63|10248.28|srle 32|
|15175482|  3.8|4609.31|9360.16|rle64 32|
|19872605|  4.9|**11299.52**|10169.71|**srle 64**|
|21910714|  5.4|8300.55|10232.33|rle64 64|
|403920058|100.0|8464.75|9160.88|memcpy|

## Compile:

        make

## Usage:

        ./trle file



Last update: 29 DEC 2015

