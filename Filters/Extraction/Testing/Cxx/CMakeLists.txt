set(test_64bit)
if(${VTK_USE_64BIT_IDS})
  set(test_64bit
    TestExtractValues.cxx,NO_VALID DATA{${_vtk_build_TEST_INPUT_DATA_DIRECTORY}/Data/cad_cubes.vtp}
    )
endif()

vtk_module_test_data(
  Data/voronoiMesh.vtu)

vtk_add_test_cxx(vtkFiltersExtractionCxxTests tests
  TestConvertSelection.cxx,NO_VALID
  TestExpandMarkedElements.cxx
  TestExtractBlock.cxx,NO_VALID,NO_DATA
  TestExtractBlockUsingDataAssembly.cxx,NO_VALID
  TestExtractCells.cxx,NO_VALID
  TestExtractDataArraysOverTime.cxx,NO_VALID
  TestExtraction.cxx
  TestExtractionExpression.cxx
  TestExtractRectilinearGrid.cxx,NO_VALID,NO_DATA
  TestExtractRows.cxx,NO_VALID,NO_DATA
  TestExtractSelectedArraysOverTime.cxx,NO_VALID
  TestExtractSelection.cxx
  TestExtractThresholdsMultiBlock.cxx,NO_VALID
  TestExtractTimeSteps.cxx,NO_VALID
  ${test_64bit}
  )
vtk_test_cxx_executable(vtkFiltersExtractionCxxTests tests)
