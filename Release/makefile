################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include MCAL/subdir.mk
-include HAL/subdir.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(ASM_DEPS)),)
-include $(ASM_DEPS)
endif
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
LSS += \
RF_Module_TX_RX.lss \

FLASH_IMAGE += \
RF_Module_TX_RX.hex \

EEPROM_IMAGE += \
RF_Module_TX_RX.eep \

SIZEDUMMY += \
sizedummy \


# All Target
all: RF_Module_TX_RX.elf secondary-outputs

# Tool invocations
RF_Module_TX_RX.elf: $(OBJS) $(USER_OBJS)
	@echo 'Building target: $@'
	@echo 'Invoking: AVR C Linker'
	avr-gcc -Wl,-Map,RF_Module_TX_RX.map -mmcu=atmega32 -o "RF_Module_TX_RX.elf" $(OBJS) $(USER_OBJS) $(LIBS)
	@echo 'Finished building target: $@'
	@echo ' '

RF_Module_TX_RX.lss: RF_Module_TX_RX.elf
	@echo 'Invoking: AVR Create Extended Listing'
	-avr-objdump -h -S RF_Module_TX_RX.elf  >"RF_Module_TX_RX.lss"
	@echo 'Finished building: $@'
	@echo ' '

RF_Module_TX_RX.hex: RF_Module_TX_RX.elf
	@echo 'Create Flash image (ihex format)'
	-avr-objcopy -R .eeprom -R .fuse -R .lock -R .signature -O ihex RF_Module_TX_RX.elf  "RF_Module_TX_RX.hex"
	@echo 'Finished building: $@'
	@echo ' '

RF_Module_TX_RX.eep: RF_Module_TX_RX.elf
	@echo 'Create eeprom image (ihex format)'
	-avr-objcopy -j .eeprom --no-change-warnings --change-section-lma .eeprom=0 -O ihex RF_Module_TX_RX.elf  "RF_Module_TX_RX.eep"
	@echo 'Finished building: $@'
	@echo ' '

sizedummy: RF_Module_TX_RX.elf
	@echo 'Invoking: Print Size'
	-avr-size --format=avr --mcu=atmega32 RF_Module_TX_RX.elf
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(FLASH_IMAGE)$(ELFS)$(OBJS)$(ASM_DEPS)$(EEPROM_IMAGE)$(S_DEPS)$(SIZEDUMMY)$(S_UPPER_DEPS)$(LSS)$(C_DEPS) RF_Module_TX_RX.elf
	-@echo ' '

secondary-outputs: $(LSS) $(FLASH_IMAGE) $(EEPROM_IMAGE) $(SIZEDUMMY)

.PHONY: all clean dependents
.SECONDARY:

-include ../makefile.targets
