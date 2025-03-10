# SCT_SC_2
#imageload
from PIL import Image
import os

# Absolute Path (Make sure it's correct)
image_path = r"C:\Users\heelm\Downloads\pexels-mrwson-4275890.jpg"

# Debugging: Check if file exists
if not os.path.exists(image_path):
    print("File not found at:", image_path)
else:
    image = Image.open(image_path)
    image.show()
    print("Done! Image loaded and displayed successfully.")

#encrypt image
from PIL import Image
import os

# Image Path (Change this to your image path)
image_path = r"C:\Users\heelm\Downloads\pexels-mrwson-4275890.jpg"

# Encryption Key (You can change this to any integer)
key = 123

# Function to Encrypt Image using XOR
def encrypt_image(image, key):
    pixels = list(image.getdata())  # Get all pixels
    new_pixels = []

    # Apply XOR operation to each pixel value
    for pixel in pixels:
        new_pixel = tuple((value ^ key) for value in pixel)
        new_pixels.append(new_pixel)

    # Create new image with modified pixels
    new_image = Image.new(image.mode, image.size)
    new_image.putdata(new_pixels)
    return new_image

# Check if image exists
if not os.path.exists(image_path):
    print("File not found at:", image_path)
else:
    # Load Image
    image = Image.open(image_path)
    image.show()
    print("Original image loaded successfully.")

    # Encrypt Image
    encrypted_image = encrypt_image(image, key)
    encrypted_image.save("encrypted_image.png")
    encrypted_image.show()
    print("Encryption completed. Encrypted image saved as 'encrypted_image.png'.")

  #decrypt image 
  from PIL import Image
import os

# Path of Encrypted Image
encrypted_image_path = "encrypted_image.png"

# Encryption Key (Same as used for encryption)
key = 123

# Function to Decrypt Image using XOR
def decrypt_image(image, key):
    pixels = list(image.getdata())  # Get all pixels
    new_pixels = []

    # Apply XOR operation to each pixel value
    for pixel in pixels:
        new_pixel = tuple((value ^ key) for value in pixel)
        new_pixels.append(new_pixel)

    # Create new image with modified pixels
    new_image = Image.new(image.mode, image.size)
    new_image.putdata(new_pixels)
    return new_image

# Check if encrypted image exists
if not os.path.exists(encrypted_image_path):
    print("Encrypted image not found at:", encrypted_image_path)
else:
    # Load Encrypted Image
    encrypted_image = Image.open(encrypted_image_path)
    encrypted_image.show()
    print("Encrypted image loaded successfully.")

    # Decrypt Image
    decrypted_image = decrypt_image(encrypted_image, key)
    decrypted_image.save("decrypted_image.png")
    decrypted_image.show()
    print("Decryption completed. Decrypted image saved as 'decrypted_image.png'.")

