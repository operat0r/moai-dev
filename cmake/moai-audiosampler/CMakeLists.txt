cmake_minimum_required ( VERSION 2.8.5 )
project ( moai-audiosampler )

set ( MOAI_AUDIOSAMPLER_INCLUDES
  "${MOAI_ROOT}/src/"
  "${MOAI_ROOT}/src/config-default/"
  )

include_directories (
  ${MOAI_AUDIOSAMPLER_INCLUDES}
)



# Use all cpp files in directory as source code
set ( MOAI_AUDIOSAMPLER_SRC
	${MOAI_ROOT}/src/moai-audiosampler/AKU-audiosampler.cpp
	${MOAI_ROOT}/src/moai-audiosampler/MOAIAudioSampler.cpp
)


add_library ( moai-audiosampler STATIC ${MOAI_AUDIOSAMPLER_SRC}  )
target_link_libraries ( moai-audiosampler moai-core moai-util moai-sim zlcore )

