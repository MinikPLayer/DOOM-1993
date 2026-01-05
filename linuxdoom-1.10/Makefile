################################################################
#
# $Id:$
#
# $Log:$
#
CC=  gcc  # gcc or g++

CFLAGS=-g -Wall -DNORMALUNIX -DLINUX -Wno-unused-const-variable -Wno-unused-but-set-variable -Wno-misleading-indentation # -DUSEASM 
LDFLAGS=-L/usr/X11R6/lib
LIBS=-lXext -lX11 -lnsl -lm

# subdirectory for objects
DIR_OUTPUT_OBJECT=linux-out
DIR_OUTPUT_BIN=linux-bin
DIR_INPUT_WADS=WADs

# not too sophisticated dependency
OBJS=				\
		$(DIR_OUTPUT_OBJECT)/doomdef.o		\
		$(DIR_OUTPUT_OBJECT)/doomstat.o		\
		$(DIR_OUTPUT_OBJECT)/dstrings.o		\
		$(DIR_OUTPUT_OBJECT)/i_system.o		\
		$(DIR_OUTPUT_OBJECT)/i_sound.o		\
		$(DIR_OUTPUT_OBJECT)/i_video.o		\
		$(DIR_OUTPUT_OBJECT)/i_net.o			\
		$(DIR_OUTPUT_OBJECT)/tables.o			\
		$(DIR_OUTPUT_OBJECT)/f_finale.o		\
		$(DIR_OUTPUT_OBJECT)/f_wipe.o 		\
		$(DIR_OUTPUT_OBJECT)/d_main.o			\
		$(DIR_OUTPUT_OBJECT)/d_net.o			\
		$(DIR_OUTPUT_OBJECT)/d_items.o		\
		$(DIR_OUTPUT_OBJECT)/g_game.o			\
		$(DIR_OUTPUT_OBJECT)/m_menu.o			\
		$(DIR_OUTPUT_OBJECT)/m_misc.o			\
		$(DIR_OUTPUT_OBJECT)/m_argv.o  		\
		$(DIR_OUTPUT_OBJECT)/m_bbox.o			\
		$(DIR_OUTPUT_OBJECT)/m_fixed.o		\
		$(DIR_OUTPUT_OBJECT)/m_swap.o			\
		$(DIR_OUTPUT_OBJECT)/m_cheat.o		\
		$(DIR_OUTPUT_OBJECT)/m_random.o		\
		$(DIR_OUTPUT_OBJECT)/am_map.o			\
		$(DIR_OUTPUT_OBJECT)/p_ceilng.o		\
		$(DIR_OUTPUT_OBJECT)/p_doors.o		\
		$(DIR_OUTPUT_OBJECT)/p_enemy.o		\
		$(DIR_OUTPUT_OBJECT)/p_floor.o		\
		$(DIR_OUTPUT_OBJECT)/p_inter.o		\
		$(DIR_OUTPUT_OBJECT)/p_lights.o		\
		$(DIR_OUTPUT_OBJECT)/p_map.o			\
		$(DIR_OUTPUT_OBJECT)/p_maputl.o		\
		$(DIR_OUTPUT_OBJECT)/p_plats.o		\
		$(DIR_OUTPUT_OBJECT)/p_pspr.o			\
		$(DIR_OUTPUT_OBJECT)/p_setup.o		\
		$(DIR_OUTPUT_OBJECT)/p_sight.o		\
		$(DIR_OUTPUT_OBJECT)/p_spec.o			\
		$(DIR_OUTPUT_OBJECT)/p_switch.o		\
		$(DIR_OUTPUT_OBJECT)/p_mobj.o			\
		$(DIR_OUTPUT_OBJECT)/p_telept.o		\
		$(DIR_OUTPUT_OBJECT)/p_tick.o			\
		$(DIR_OUTPUT_OBJECT)/p_saveg.o		\
		$(DIR_OUTPUT_OBJECT)/p_user.o			\
		$(DIR_OUTPUT_OBJECT)/r_bsp.o			\
		$(DIR_OUTPUT_OBJECT)/r_data.o			\
		$(DIR_OUTPUT_OBJECT)/r_draw.o			\
		$(DIR_OUTPUT_OBJECT)/r_main.o			\
		$(DIR_OUTPUT_OBJECT)/r_plane.o		\
		$(DIR_OUTPUT_OBJECT)/r_segs.o			\
		$(DIR_OUTPUT_OBJECT)/r_sky.o			\
		$(DIR_OUTPUT_OBJECT)/r_things.o		\
		$(DIR_OUTPUT_OBJECT)/w_wad.o			\
		$(DIR_OUTPUT_OBJECT)/wi_stuff.o		\
		$(DIR_OUTPUT_OBJECT)/v_video.o		\
		$(DIR_OUTPUT_OBJECT)/st_lib.o			\
		$(DIR_OUTPUT_OBJECT)/st_stuff.o		\
		$(DIR_OUTPUT_OBJECT)/hu_stuff.o		\
		$(DIR_OUTPUT_OBJECT)/hu_lib.o			\
		$(DIR_OUTPUT_OBJECT)/s_sound.o		\
		$(DIR_OUTPUT_OBJECT)/z_zone.o			\
		$(DIR_OUTPUT_OBJECT)/info.o				\
		$(DIR_OUTPUT_OBJECT)/sounds.o

all : create_output_directories $(DIR_OUTPUT_OBJECT)/linuxxdoom copy_bin

clean:
	rm -f *.o *~ *.flc
	rm -rf $(DIR_OUTPUT_OBJECT)

create_output_directories:
	mkdir -p $(DIR_OUTPUT_OBJECT)
	mkdir -p $(DIR_OUTPUT_BIN)

copy_bin:
	cp $(DIR_OUTPUT_OBJECT)/linuxxdoom $(DIR_OUTPUT_BIN)
	cp -r $(DIR_INPUT_WADS)/* $(DIR_OUTPUT_BIN)/

$(DIR_OUTPUT_OBJECT)/linuxxdoom:  $(OBJS) $(DIR_OUTPUT_OBJECT)/i_main.o
	$(CC) $(CFLAGS) $(LDFLAGS) $(OBJS) $(DIR_OUTPUT_OBJECT)/i_main.o \
	-o $(DIR_OUTPUT_OBJECT)/linuxxdoom $(LIBS)

$(DIR_OUTPUT_OBJECT)/%.o:	%.c
	$(CC) $(CFLAGS) -c $< -o $@

#############################################################
#
#############################################################