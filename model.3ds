import bpy

# Clear existing mesh objects
bpy.ops.wm.read_factory_settings(use_empty=True)

# Create a new cube
bpy.ops.mesh.primitive_cube_add(size=2, enter_editmode=False, align='WORLD', location=(0, 0, 0))

# Access the cube object
cube = bpy.context.object

# Modify cube properties (e.g., scale, location, rotation)
cube.scale = (1, 1, 1)
cube.location = (0, 0, 1)
cube.rotation_euler = (0, 0, 0)

# Create a new material for the cube
mat = bpy.data.materials.new(name="CubeMaterial")
cube.data.materials.append(mat)

# Set material properties (e.g., color)
mat.diffuse_color = (0.8, 0.2, 0.2, 1.0)  # Red color

# Render settings (optional)
bpy.context.scene.render.engine = 'CYCLES'
bpy.context.scene.cycles.samples = 200

# Set up camera (optional)
bpy.ops.object.camera_add(location=(6, -6, 6))
camera = bpy.context.object
bpy.context.scene.camera = camera

# Set camera parameters (e.g., focal length, rotation)
camera.data.lens = 50
camera.rotation_euler = (1.0, 0.0, 0.8)

# Render the scene (optional)
bpy.ops.render.render(write_still=True)

# Save the blend file (optional)
bpy.ops.wm.save_mainfile(filepath="architectural_model.blend")
