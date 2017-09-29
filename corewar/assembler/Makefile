# ----- Colors -----
BLACK ="\033[1;30m"
RED ="\033[1;31m"
GREEN ="\033[1;32m"
YELLOW = "\x1b[33m"
BLUE = "\x1b[34m"
MAGENTA = "\x1b[35m"
CYAN ="\033[1;35m"
PURPLE ="\033[1;36m"
WHITE ="\033[1;37m"
EOC ="\033[0;0m"
RESET = "\x1b[0m"
# ==================

LIB = libft.a

NAME = asm
HEAD = header/asm.h header/other.h header/func.h

# FLAGS = -Wall -Wextra -Werror

#------ path -------
FILES_PATH		= ./files
OTHER_PATH		= ./files/other
FILL_PATH		= ./files/fill
VALIDATE_PATH	= ./files/validate
OBJECTS_PATH	= ./objects


#------ files ------
FILES_FILES		= main
OTHER_FILES		= struct_create other print_error
FILL_FILES		= fill_arguments commands
VALIDATE_FILES	= label_command header check

#------ other ------
FILES_OBJ 		= $(addprefix $(OBJECTS_PATH)/, $(addsuffix .o, $(FILES_FILES)))
OTHER_OBG 		= $(addprefix $(OBJECTS_PATH)/, $(addsuffix .o, $(OTHER_FILES)))
FILL_OBG		= $(addprefix $(OBJECTS_PATH)/, $(addsuffix .o, $(FILL_FILES)))
VALIDATE_OBJ	= $(addprefix $(OBJECTS_PATH)/, $(addsuffix .o, $(VALIDATE_FILES)))

#------ make ------
all: $(NAME)

$(NAME): $(FILES_OBJ) $(OTHER_OBG) $(FILL_OBG) $(VALIDATE_OBJ)
	@echo "\n"
	@make -C ../libft/
	@echo $(CYAN) "\tCompiling $@"$(RESET)
	@gcc $(FLAGS) -o $@ $^ ../libft/libft.a
	@echo $(GREEN) "\tasm\t\t- has been made\n"$(RESET)

$(OBJECTS_PATH)/%.o: $(VALIDATE_PATH)/%.c
	@echo $(PURPLE) "\tCompiling $<"$(RESET)
	@mkdir $(OBJECTS_PATH) 2> /dev/null || true
	@gcc $(FLAGS) -o $@ -c $<

$(OBJECTS_PATH)/%.o: $(FILES_PATH)/%.c
	@echo $(PURPLE) "\tCompiling $<"$(RESET)
	@mkdir $(OBJECTS_PATH) 2> /dev/null || true
	@gcc $(FLAGS) -o $@ -c $<

$(OBJECTS_PATH)/%.o: $(OTHER_PATH)/%.c
	@echo $(PURPLE) "\tCompiling $<"$(RESET)
	@mkdir $(OBJECTS_PATH) 2> /dev/null || true
	@gcc $(FLAGS) -o $@ -c $<

$(OBJECTS_PATH)/%.o: $(FILL_PATH)/%.c
	@echo $(PURPLE) "\tCompiling $<"$(RESET)
	@mkdir $(OBJECTS_PATH) 2> /dev/null || true
	@gcc $(FLAGS) -o $@ -c $<

#------ make clean ------
cleanlib:
	# @make clean -C ../libft

clean: cleanlib
	@echo $(YELLOW)"\t\t\t\tASSEMBLER"$(RESET)
	@rm -f $(HEART_OBJ)
	@rm -f $(OTHER_OBG)
	@rm -f $(FUNC_OBG)
	@echo $(RED) "\t.o files have been cleaned.\n"$(RESET)

#------ make fclean ------
fcleanlib:
	# @make fclean -C ../libft

fclean: fcleanlib
	@echo $(YELLOW)"\t\t\t\tASSEMBLER"$(RESET)
	@rm -f $(HEART_OBJ)
	@rm -f $(OTHER_OBG)
	@rm -f $(FUNC_OBG)
	@echo $(RED)"\t.o files have been cleaned."$(RESET)
	@rm -rf $(OBJECTS_PATH)
	@echo $(RED) "\t./objects path have been cleaned."$(RESET)
	@rm -f $(NAME)
	@echo $(RED) "\tasm have been cleaned.\n"$(RESET)

#------ make re ------
re: fclean all