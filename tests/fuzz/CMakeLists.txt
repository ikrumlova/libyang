cmake_minimum_required(VERSION 2.8.12)

set(fuzz_targets yangfuzz xmlfuzz jsonfuzz lybfuzz xml_lyd_parse_path_fuzz yinfuzz)

foreach(target_name IN LISTS fuzz_targets)
    add_executable(${target_name} ${target_name}.c)
    target_link_libraries(${target_name} yang)
endforeach(target_name)
