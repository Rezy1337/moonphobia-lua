# Cheat

Доступные функции для первичного взаимодействия с читом

```bash
	run_script("name.lua") //Запуск скрипта из папки lua
	reload_active_scripts() //Перезапускает активные скрипты
	is_key_down() //Проверяет нажатие клавиши
    	get_tick_count() //Возвращает количество тиков
    	play_sound("name.wav") //Проигрывает звук из папки lua, поддерживает только .wav формат.
	set_event_callback() //Вызов функции в определенном хуке
	void load_cfg(string name);
	void chatprint(string string1,...);
	const char* GetAppData();
	bool is_key_down(int key);
	bool IsKeyDown(int key);
	patternscan(string module, string mask)
	mkdir(string patch)
```

Пример использования

Типы callback: "paint_traverse","create_move","fire_event"

```lua
cheat.set_event_callback("paint_traverse", funcName)
```

Пример с клантегом:
```lua
function DoClanTag()
    local lplayer = engine.get_local_player_index()
    if lplayer then
   
            utils.setclantag("moonphobia")
           
    end
end

cheat.set_event_callback("paint_traverse", DoClanTag)
```

## ui
```bash
	void add_button(string label, (optional) void cb);
	void add_checkbox(string label, string unique_id, (optional) bool def);
	void add_text(string label);
	void add_slider_int(string label, string unique_id, int min, int max, (optional) int def, (optional) string format);
	void add_slider_float(string label, string unique_id, (optional) float min, (optional) float max, (optional) float def, (optional) float power, (optional) string format);
	void add_hotkey(string name, string unique_id);
	void add_combo(string name, string unique_id, string-array);
	void set_window_size(int x, int y);
	void set_window_title(string title);
	float get_float_value(string unique_id);
	int get_hk_value(string unique_id);
	int get_combo_value(string unique_id);
	int get_int_value(string unique_id);
	bool get_cb_value(string unique_id);
```

## entity
```bash
	C_BaseEntity* get_client_entity(int idx);
	int number_of_entities(bool b);
	int get_highest_entity_index();
	C_BaseEntity* get_client_entity_from_handle(ULONG ent);
	C_BaseEntity* get_ent(int entNum);
	C_BasePlayer* get_player(int entNum);
	int classID(int entNum);
	string className(int entNum);
```

## ClientEngine


```bash
	client_cmd(std::string cmd) 
	client_cmd_unrestricted(std::string cmd) 
	execute_client_cmd(std::string cmd) //Выполнить команду в консоли
	get_app_id() //Получить айди игры 
	get_engine_build_number() //Получить номер сборки игры
	get_game_directory() //Получить папку расположения игры
	get_last_timestamp() //Получить timestamp (дату и время в UNIX формате)
	get_level_name() //Получить название карты
	get_level_name_short() //Получить короткое название карты
	get_local_player_index() //Получить локального игрока
	get_map_group_name() 
	get_max_clients() 
	get_mouse_delta()
	get_netchannel() //Получить class netchannel
	get_net_channel_info() //Получить class netchannel info
	get_player_for_user_id(int userid) //Получить игрока по id
	get_player_info(int ent) //Получить информацию о игроке
	get_product_version_string() 
	get_screen_size() //Получить размеры экрана
	get_timescale() //Получить скоросить игры
	get_view_angles() //Получить viewangels
	is_connected() //Проверка на подключение
	is_hammer_running()
	is_hltv() //Проверка на HLTV
	is_in_game() //Проверка, в игре ли
	is_low_violence()
	is_occluded(Vector mins, Vector maxs)
	is_paused() //Проверка на паузу
	is_playing_demo() //Проверка на проигрывание демо
	is_recording_demo() //Проверка на запись демо
	is_taking_screenshot() //Проверка на скриншот
	level_leaf_count() 
	map_has_hdr_lighting()
	remove_all_paint()
	set_blur_fade(float amt) //Установка blur
	set_restrict_client_commands(bool v)
	set_timescale(float t) //Установка скорости игры
	set_view_angles(QAngle va) //Установка viewangels
	supports_hdr()
	write_screenshot(std::string filename) //Сделать скриншот
	m_vecOrigin(C_BasePlayer* ent)
	ip()
```

## Global


```bash
    curtime() 
    tickcount()
    framecount()
    absoluteframetime()
    frametime()
    maxclients()
    realtime()
    tickinterval()
```

## Render


```bash
	render_text(const std::string& text, int x, int y, float size,Color color) //Рендер текста
    render_box_filled(float x1, float y1, float x2, float y2,Color color) //Рендер бокса с заполнением
    render_line(int x1,int y1,int x2,int y2,Color color) //Рендер линии
    render_box(float x1, float y1, float x2, float y2,Color color) //Рендер бокса
    render_circle(int x,int y,float radius,int points,Color color) //Рендер круга
    createbeam(BeamInfo_t beam)
    worldtoscreen(Vector* pos, Vector* end)
```

## CVar


```bash
	console_print(sol::variadic_args args) //Вывод в консоль
    console_print_color(int r,int g,int b,sol::variadic_args args) //Вывод в консоль цветом
    find_cvar(std::string name) //Найти квар
    set_int(ConVar* var, int i) //Установка integer
    get_int(ConVar* var) //Получение integer
    get_float(ConVar* var) //Получение float
    set_float(ConVar* var, float f) //Установка float
    get_command_line_value(std::string var) 
    get_string(ConVar* var, string value)
    set_string(ConVar* var, string value)
```

## Utils


```bash
set_clantag(const char* tag) //Установка клантега
get_offset(const std::string& tableName, const std::string& propName) //Получение оффсета
is_local()
get_time()
urldownloadfile(string DownloadFrom_URL, string DownloadTo_Patch)
CCSWeaponInfo* weapondata()
```

## Examples


?> Вы можете скачать простые примеры по ссылке (https://vk.cc/ae1bOl)
