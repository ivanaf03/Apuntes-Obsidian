[[Elixir]]

```elixir
defmodule PaintByNumber do
  def palette_bit_size(color_count) do
    ceil(:math.log(color_count) / :math.log(2))
  end

  def empty_picture() do
    <<>>
  end

  def test_picture() do
    <<00::2, 01::2, 10::2, 11::2>>
  end

def prepend_pixel(picture, color_count, pixel_color_index) do
  <<pixel_color_index::size(palette_bit_size(color_count)), picture::bitstring>>
  end

  def get_first_pixel(<<>>, _color_count) do
    nil
  end

  def get_first_pixel(picture, color_count) do
    palette_size = palette_bit_size(color_count)
    <<first_pixel::size(palette_size), _rest::bitstring>> = picture
    first_pixel
  end

  def drop_first_pixel(<<>>, _color_count) do
    <<>>
  end

  def drop_first_pixel(picture, color_count) do
    palette_size = palette_bit_size(color_count)
    <<_first_pixel::size(palette_size), rest::bitstring>> = picture
    rest
  end

  def concat_pictures(picture1, picture2) do
    <<picture1::bitstring, picture2::bitstring>>
  end
end

```