# SPI

## 数据结构

spi_transfer

	struct spi_transfer - a read/write buffer pair
	@tx_buf: data to be written (dma-safe memory), or NULL
	@rx_buf: data to be read (dma-safe memory), or NULL
	@len: size of rx and tx buffers (in bytes)
	@cs_change: affects chipselect after this transfer completes

## Debug

read and write test

	cat /dev/ttysWK0
	echo 1 > /dev/ttysWK0

测试脚本

	i=1
	while true
	do
	if [ $i -eq 10 ]
	then
	(( i=1 ))
	fi
	echo $i > /dev/ttysWK0
	sleep 1
	(( i+=1 ))
	done
