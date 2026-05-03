# релиз ядра
KREL := $(shell uname -r)
CC := $(shell grep CONFIG_CC_VERSION /boot/config-$(KREL) | cut -d'"' -f2 | awk '{print $$1}')

KDIR := /lib/modules/$(KREL)/build

# куда вернуться
PWD := $(shell pwd)

TARGET := hello_printk

obj-m := $(TARGET).o

all:
	$(MAKE) CC=$(CC) -C $(KDIR) M=$(PWD) modules

clean:
	$(MAKE) -C $(KDIR) M=$(PWD) clean