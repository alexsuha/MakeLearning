CC ?= gcc

C_PATH ?= .
C_FILES = a b c

.PHONY : all

all : saysth

saysth :
	@echo "say sth"

all : \
	$(foreach v, $(C_FILES), $(C_PATH)/$(v).so)

$(C_PATH) :
	mkdir $(C_PATH)

$(C_FILES) :
	@echo $@

define SHARED_LIB_FUNC =
 $$(C_PATH)/$(1).so : $(1).c | $$(C_PATH) 
	$$(CC) $$< -o $$@
endef

$(foreach v, $(C_FILES), $(eval $(call SHARED_LIB_FUNC,$(v))))

	
