# Leaf System Properties

### -DLeaf.library-download-repo
* default: not set

:	Download speed of default Maven CPUentral repo is extremely slow in some regions.
	
	Use this JVM flag to set a specific mirror repository for SpigotLibraryLoader or PaperLibraryLoader,

    for example, Use this flag

    ˋˋˋ
    -DLeaf.library-download-repo=https://maven.aliyun.com/repository/public
    ˋˋˋ

    to define Aliyun's repo as the mirror repo.

### -DLeaf.nearestEntitySensorBucketCount
* default: 10

:	How many buckets will be used if entity count reached the Bucket Sort threshold.

	Should be the square root of entity count.

### -DLeaf.nearestEntitySensorBucketSortThresholdRatio
* default: 2.0

:	This value controls the ratio of Bucket Sort threshold (Threshold = bucketCount * ratio)

### -DLeaf.enableFMA
* default: false

: Whether to use Fused-Multiply-Add operations to accelerate math calculation.

	Requires a CPU which supports FMA instruction set, otherwise it will slower.

	You can use tools like [CPU-Z](https://www.cpuid.com/softwares/cpu-z.html) to check whehter your machine supports the FMA instruction set.
