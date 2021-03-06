# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: chahan <hgdst14@naver.com>                 +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2021/11/18 13:10:24 by chahan            #+#    #+#              #
#    Updated: 2021/11/18 13:10:25 by chahan           ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

NAME = libft.a
INCLUDE = ../include
SRCS_DIR = src/
OBJS_DIR = obj/
CC = gcc
FLAGS = -Wall -Wextra -Werror -I
RM = rm -f
AR = ar rcs

#Colors

DEF_COLOR = \033[0;39m
GRAY = \033[0;90m
RED = \033[0;91m
GREEN = \033[0;92m
YELLOW = \033[0;93m
BLUE = \033[0;94m
MAGENTA = \033[0;95m
CYAN = \033[0;96m
WHITE = \033[0;97m

# SRCS

FTIS_DIR = ft_is/
FTIS = ft_isalnum ft_isalpha ft_isascii ft_isdigit ft_isprint

FTLST_DIR = ft_lst/
FTLST = ft_lstadd_back ft_lstadd_front ft_lstclear ft_lstdelone ft_lstiter ft_lstlast ft_lstmap ft_lstnew ft_lstsize

FTMEM_DIR = ft_mem/
FTMEM = ft_bzero ft_calloc ft_memccpy ft_memchr ft_memcmp ft_memcpy ft_memmove ft_memset

FTPUT_DIR = ft_put/
FTPUT = ft_putchar_fd ft_putendl_fd ft_putnbr_fd ft_putstr_fd

FTSTR_DIR = ft_str/
FTSTR = ft_split ft_strchr ft_strcmp ft_strdup ft_strjoin ft_strlcat ft_strlcpy ft_strlen ft_strmapi ft_strncmp ft_strnstr ft_strrchr ft_strtrim ft_substr

FTTO_DIR = ft_to/
FTTO = ft_atoi ft_itoa ft_tolower ft_toupper

SRC_FILES += $(addprefix $(FTIS_DIR), $(FTIS))
SRC_FILES += $(addprefix $(FTLST_DIR), $(FTLST))
SRC_FILES += $(addprefix $(FTMEM_DIR), $(FTMEM))
SRC_FILES += $(addprefix $(FTPUT_DIR), $(FTPUT))
SRC_FILES += $(addprefix $(FTSTR_DIR), $(FTSTR))
SRC_FILES += $(addprefix $(FTTO_DIR), $(FTTO))

SRCS = $(addprefix $(SRCS_DIR), $(addsuffix .c, $(SRC_FILES)))
OBJS = $(addprefix $(OBJS_DIR), $(addsuffix .o, $(SRC_FILES)))
OBJSF		=	.cache_exists

all:		$(NAME)

$(NAME):	$(OBJS)
			@$(AR) $(NAME) $(OBJS)
			@ranlib $(NAME)
			@echo "$(GREEN)Libft compiled!$(DEF_COLOR)"

$(OBJS_DIR)%.o : $(SRCS_DIR)%.c | $(OBJSF)
			@echo "$(YELLOW)Compiling: $< $(DEF_COLOR)"
			@$(CC) $(CFLAGS) $(INCLUDES) -c $< -o $@

$(OBJSF):
			@mkdir -p $(OBJS_DIR)
			@mkdir -p $(OBJS_DIR)$(FTIS_DIR)
			@mkdir -p $(OBJS_DIR)$(FTMEM_DIR)
			@mkdir -p $(OBJS_DIR)$(FTPUT_DIR)
			@mkdir -p $(OBJS_DIR)$(FTTO_DIR)
			@mkdir -p $(OBJS_DIR)$(FTSTR_DIR)
			@mkdir -p $(OBJS_DIR)$(FTLST_DIR)

clean:
			@$(RM) -rf $(OBJS_DIR)
			@$(RM) -f $(OBJSF)
			@echo "$(BLUE)libft objects files cleaned!$(DEF_COLOR)"

fclean:		clean
			@$(RM) -f $(NAME)
			@echo "$(CYAN)libft executable files cleaned!$(DEF_COLOR)"

re:			fclean all
			@echo "$(GREEN)Cleaned and rebuilt everything for libft!$(DEF_COLOR)"

norm:
	@norminette $(SRCS) $(INCLUDES) | grep -v Norme -B1 || true

.PHONY:		all clean fclean re norm
