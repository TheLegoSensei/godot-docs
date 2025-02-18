:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the Decal.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_Decal:

Decal
=====

**Inherits:** :ref:`VisualInstance3D<class_VisualInstance3D>` **<** :ref:`Node3D<class_Node3D>` **<** :ref:`Node<class_Node>` **<** :ref:`Object<class_Object>`

Node that projects a texture onto a :ref:`MeshInstance3D<class_MeshInstance3D>`.

Description
-----------

``Decal``\ s are used to project a texture onto a :ref:`Mesh<class_Mesh>` in the scene. Use Decals to add detail to a scene without affecting the underlying :ref:`Mesh<class_Mesh>`. They are often used to add weathering to building, add dirt or mud to the ground, or add variety to props. Decals can be moved at any time, making them suitable for things like blob shadows or laser sight dots.

They are made of an :ref:`AABB<class_AABB>` and a group of :ref:`Texture2D<class_Texture2D>`\ s specifying :ref:`Color<class_Color>`, normal, ORM (ambient occlusion, roughness, metallic), and emission. Decals are projected within their :ref:`AABB<class_AABB>` so altering the orientation of the Decal affects the direction in which they are projected. By default, Decals are projected down (i.e. from positive Y to negative Y).

The :ref:`Texture2D<class_Texture2D>`\ s associated with the Decal are automatically stored in a texture atlas which is used for drawing the decals so all decals can be drawn at once. Godot uses clustered decals, meaning they are stored in cluster data and drawn when the mesh is drawn, they are not drawn as a post-processing effect after.

\ **Note:** Decals cannot affect an underlying material's transparency, regardless of its transparency mode (alpha blend, alpha scissor, alpha hash, opaque pre-pass). This means translucent or transparent areas of a material will remain translucent or transparent even if an opaque decal is applied on them.

Properties
----------

+-----------------------------------+--------------------------------------------------------------------------+-----------------------+
| :ref:`float<class_float>`         | :ref:`albedo_mix<class_Decal_property_albedo_mix>`                       | ``1.0``               |
+-----------------------------------+--------------------------------------------------------------------------+-----------------------+
| :ref:`int<class_int>`             | :ref:`cull_mask<class_Decal_property_cull_mask>`                         | ``1048575``           |
+-----------------------------------+--------------------------------------------------------------------------+-----------------------+
| :ref:`float<class_float>`         | :ref:`distance_fade_begin<class_Decal_property_distance_fade_begin>`     | ``10.0``              |
+-----------------------------------+--------------------------------------------------------------------------+-----------------------+
| :ref:`bool<class_bool>`           | :ref:`distance_fade_enabled<class_Decal_property_distance_fade_enabled>` | ``false``             |
+-----------------------------------+--------------------------------------------------------------------------+-----------------------+
| :ref:`float<class_float>`         | :ref:`distance_fade_length<class_Decal_property_distance_fade_length>`   | ``1.0``               |
+-----------------------------------+--------------------------------------------------------------------------+-----------------------+
| :ref:`float<class_float>`         | :ref:`emission_energy<class_Decal_property_emission_energy>`             | ``1.0``               |
+-----------------------------------+--------------------------------------------------------------------------+-----------------------+
| :ref:`Vector3<class_Vector3>`     | :ref:`extents<class_Decal_property_extents>`                             | ``Vector3(1, 1, 1)``  |
+-----------------------------------+--------------------------------------------------------------------------+-----------------------+
| :ref:`float<class_float>`         | :ref:`lower_fade<class_Decal_property_lower_fade>`                       | ``0.3``               |
+-----------------------------------+--------------------------------------------------------------------------+-----------------------+
| :ref:`Color<class_Color>`         | :ref:`modulate<class_Decal_property_modulate>`                           | ``Color(1, 1, 1, 1)`` |
+-----------------------------------+--------------------------------------------------------------------------+-----------------------+
| :ref:`float<class_float>`         | :ref:`normal_fade<class_Decal_property_normal_fade>`                     | ``0.0``               |
+-----------------------------------+--------------------------------------------------------------------------+-----------------------+
| :ref:`Texture2D<class_Texture2D>` | :ref:`texture_albedo<class_Decal_property_texture_albedo>`               |                       |
+-----------------------------------+--------------------------------------------------------------------------+-----------------------+
| :ref:`Texture2D<class_Texture2D>` | :ref:`texture_emission<class_Decal_property_texture_emission>`           |                       |
+-----------------------------------+--------------------------------------------------------------------------+-----------------------+
| :ref:`Texture2D<class_Texture2D>` | :ref:`texture_normal<class_Decal_property_texture_normal>`               |                       |
+-----------------------------------+--------------------------------------------------------------------------+-----------------------+
| :ref:`Texture2D<class_Texture2D>` | :ref:`texture_orm<class_Decal_property_texture_orm>`                     |                       |
+-----------------------------------+--------------------------------------------------------------------------+-----------------------+
| :ref:`float<class_float>`         | :ref:`upper_fade<class_Decal_property_upper_fade>`                       | ``0.3``               |
+-----------------------------------+--------------------------------------------------------------------------+-----------------------+

Methods
-------

+-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Texture2D<class_Texture2D>` | :ref:`get_texture<class_Decal_method_get_texture>` **(** :ref:`DecalTexture<enum_Decal_DecalTexture>` type **)** |const|                                    |
+-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                              | :ref:`set_texture<class_Decal_method_set_texture>` **(** :ref:`DecalTexture<enum_Decal_DecalTexture>` type, :ref:`Texture2D<class_Texture2D>` texture **)** |
+-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+

Enumerations
------------

.. _enum_Decal_DecalTexture:

.. _class_Decal_constant_TEXTURE_ALBEDO:

.. _class_Decal_constant_TEXTURE_NORMAL:

.. _class_Decal_constant_TEXTURE_ORM:

.. _class_Decal_constant_TEXTURE_EMISSION:

.. _class_Decal_constant_TEXTURE_MAX:

enum **DecalTexture**:

- **TEXTURE_ALBEDO** = **0** --- :ref:`Texture2D<class_Texture2D>` corresponding to :ref:`texture_albedo<class_Decal_property_texture_albedo>`.

- **TEXTURE_NORMAL** = **1** --- :ref:`Texture2D<class_Texture2D>` corresponding to :ref:`texture_normal<class_Decal_property_texture_normal>`.

- **TEXTURE_ORM** = **2** --- :ref:`Texture2D<class_Texture2D>` corresponding to :ref:`texture_orm<class_Decal_property_texture_orm>`.

- **TEXTURE_EMISSION** = **3** --- :ref:`Texture2D<class_Texture2D>` corresponding to :ref:`texture_emission<class_Decal_property_texture_emission>`.

- **TEXTURE_MAX** = **4** --- Max size of :ref:`DecalTexture<enum_Decal_DecalTexture>` enum.

Property Descriptions
---------------------

.. _class_Decal_property_albedo_mix:

- :ref:`float<class_float>` **albedo_mix**

+-----------+-----------------------+
| *Default* | ``1.0``               |
+-----------+-----------------------+
| *Setter*  | set_albedo_mix(value) |
+-----------+-----------------------+
| *Getter*  | get_albedo_mix()      |
+-----------+-----------------------+

Blends the albedo :ref:`Color<class_Color>` of the decal with albedo :ref:`Color<class_Color>` of the underlying mesh.

----

.. _class_Decal_property_cull_mask:

- :ref:`int<class_int>` **cull_mask**

+-----------+----------------------+
| *Default* | ``1048575``          |
+-----------+----------------------+
| *Setter*  | set_cull_mask(value) |
+-----------+----------------------+
| *Getter*  | get_cull_mask()      |
+-----------+----------------------+

Specifies which :ref:`VisualInstance3D.layers<class_VisualInstance3D_property_layers>` this decal will project on. By default, Decals affect all layers. This is used so you can specify which types of objects receive the Decal and which do not. This is especially useful so you can ensure that dynamic objects don't accidentally receive a Decal intended for the terrain under them.

----

.. _class_Decal_property_distance_fade_begin:

- :ref:`float<class_float>` **distance_fade_begin**

+-----------+--------------------------------+
| *Default* | ``10.0``                       |
+-----------+--------------------------------+
| *Setter*  | set_distance_fade_begin(value) |
+-----------+--------------------------------+
| *Getter*  | get_distance_fade_begin()      |
+-----------+--------------------------------+

Distance from the camera at which the Decal begins to fade away.

----

.. _class_Decal_property_distance_fade_enabled:

- :ref:`bool<class_bool>` **distance_fade_enabled**

+-----------+---------------------------------+
| *Default* | ``false``                       |
+-----------+---------------------------------+
| *Setter*  | set_enable_distance_fade(value) |
+-----------+---------------------------------+
| *Getter*  | is_distance_fade_enabled()      |
+-----------+---------------------------------+

If ``true``, decals will smoothly fade away when far from the active :ref:`Camera3D<class_Camera3D>` starting at :ref:`distance_fade_begin<class_Decal_property_distance_fade_begin>`. The Decal will fade out over :ref:`distance_fade_length<class_Decal_property_distance_fade_length>`, after which it will be culled and not sent to the shader at all. Use this to reduce the number of active Decals in a scene and thus improve performance.

----

.. _class_Decal_property_distance_fade_length:

- :ref:`float<class_float>` **distance_fade_length**

+-----------+---------------------------------+
| *Default* | ``1.0``                         |
+-----------+---------------------------------+
| *Setter*  | set_distance_fade_length(value) |
+-----------+---------------------------------+
| *Getter*  | get_distance_fade_length()      |
+-----------+---------------------------------+

Distance over which the Decal fades. The Decal becomes slowly more transparent over this distance and is completely invisible at the end.

----

.. _class_Decal_property_emission_energy:

- :ref:`float<class_float>` **emission_energy**

+-----------+----------------------------+
| *Default* | ``1.0``                    |
+-----------+----------------------------+
| *Setter*  | set_emission_energy(value) |
+-----------+----------------------------+
| *Getter*  | get_emission_energy()      |
+-----------+----------------------------+

Energy multiplier for the emission texture. This will make the decal emit light at a higher intensity.

----

.. _class_Decal_property_extents:

- :ref:`Vector3<class_Vector3>` **extents**

+-----------+----------------------+
| *Default* | ``Vector3(1, 1, 1)`` |
+-----------+----------------------+
| *Setter*  | set_extents(value)   |
+-----------+----------------------+
| *Getter*  | get_extents()        |
+-----------+----------------------+

Sets the size of the :ref:`AABB<class_AABB>` used by the decal. The AABB goes from ``-extents`` to ``extents``.

----

.. _class_Decal_property_lower_fade:

- :ref:`float<class_float>` **lower_fade**

+-----------+-----------------------+
| *Default* | ``0.3``               |
+-----------+-----------------------+
| *Setter*  | set_lower_fade(value) |
+-----------+-----------------------+
| *Getter*  | get_lower_fade()      |
+-----------+-----------------------+

Sets the curve over which the decal will fade as the surface gets further from the center of the :ref:`AABB<class_AABB>`.

----

.. _class_Decal_property_modulate:

- :ref:`Color<class_Color>` **modulate**

+-----------+-----------------------+
| *Default* | ``Color(1, 1, 1, 1)`` |
+-----------+-----------------------+
| *Setter*  | set_modulate(value)   |
+-----------+-----------------------+
| *Getter*  | get_modulate()        |
+-----------+-----------------------+

Changes the :ref:`Color<class_Color>` of the Decal by multiplying it with this value.

----

.. _class_Decal_property_normal_fade:

- :ref:`float<class_float>` **normal_fade**

+-----------+------------------------+
| *Default* | ``0.0``                |
+-----------+------------------------+
| *Setter*  | set_normal_fade(value) |
+-----------+------------------------+
| *Getter*  | get_normal_fade()      |
+-----------+------------------------+

Fades the Decal if the angle between the Decal's :ref:`AABB<class_AABB>` and the target surface becomes too large. A value of ``0`` projects the Decal regardless of angle, a value of ``1`` limits the Decal to surfaces that are nearly perpendicular.

----

.. _class_Decal_property_texture_albedo:

- :ref:`Texture2D<class_Texture2D>` **texture_albedo**

+----------+--------------------+
| *Setter* | set_texture(value) |
+----------+--------------------+
| *Getter* | get_texture()      |
+----------+--------------------+

:ref:`Texture2D<class_Texture2D>` with the base :ref:`Color<class_Color>` of the Decal. Either this or the :ref:`texture_emission<class_Decal_property_texture_emission>` must be set for the Decal to be visible. Use the alpha channel like a mask to smoothly blend the edges of the decal with the underlying object.

----

.. _class_Decal_property_texture_emission:

- :ref:`Texture2D<class_Texture2D>` **texture_emission**

+----------+--------------------+
| *Setter* | set_texture(value) |
+----------+--------------------+
| *Getter* | get_texture()      |
+----------+--------------------+

:ref:`Texture2D<class_Texture2D>` with the emission :ref:`Color<class_Color>` of the Decal. Either this or the :ref:`texture_emission<class_Decal_property_texture_emission>` must be set for the Decal to be visible. Use the alpha channel like a mask to smoothly blend the edges of the decal with the underlying object.

----

.. _class_Decal_property_texture_normal:

- :ref:`Texture2D<class_Texture2D>` **texture_normal**

+----------+--------------------+
| *Setter* | set_texture(value) |
+----------+--------------------+
| *Getter* | get_texture()      |
+----------+--------------------+

:ref:`Texture2D<class_Texture2D>` with the per-pixel normal map for the decal. Use this to add extra detail to decals.

----

.. _class_Decal_property_texture_orm:

- :ref:`Texture2D<class_Texture2D>` **texture_orm**

+----------+--------------------+
| *Setter* | set_texture(value) |
+----------+--------------------+
| *Getter* | get_texture()      |
+----------+--------------------+

:ref:`Texture2D<class_Texture2D>` storing ambient occlusion, roughness, and metallic for the decal. Use this to add extra detail to decals.

----

.. _class_Decal_property_upper_fade:

- :ref:`float<class_float>` **upper_fade**

+-----------+-----------------------+
| *Default* | ``0.3``               |
+-----------+-----------------------+
| *Setter*  | set_upper_fade(value) |
+-----------+-----------------------+
| *Getter*  | get_upper_fade()      |
+-----------+-----------------------+

Sets the curve over which the decal will fade as the surface gets further from the center of the :ref:`AABB<class_AABB>`.

Method Descriptions
-------------------

.. _class_Decal_method_get_texture:

- :ref:`Texture2D<class_Texture2D>` **get_texture** **(** :ref:`DecalTexture<enum_Decal_DecalTexture>` type **)** |const|

Returns the :ref:`Texture2D<class_Texture2D>` associated with the specified :ref:`DecalTexture<enum_Decal_DecalTexture>`. This is a convenience method, in most cases you should access the texture directly.

For example, instead of ``albedo_tex = $Decal.get_texture(Decal.TEXTURE_ALBEDO)``, use ``albedo_tex = $Decal.texture_albedo``.

One case where this is better than accessing the texture directly is when you want to copy one Decal's textures to another. For example:


.. tabs::

 .. code-tab:: gdscript

    for i in Decal.TEXTURE_MAX:
        $NewDecal.set_texture(i, $OldDecal.get_texture(i))

 .. code-tab:: csharp

    for (int i = 0; i < (int)Decal.DecalTexture.Max; i++)
    {
        GetNode<Decal>("NewDecal").SetTexture(i, GetNode<Decal>("OldDecal").GetTexture(i));
    }



----

.. _class_Decal_method_set_texture:

- void **set_texture** **(** :ref:`DecalTexture<enum_Decal_DecalTexture>` type, :ref:`Texture2D<class_Texture2D>` texture **)**

Sets the :ref:`Texture2D<class_Texture2D>` associated with the specified :ref:`DecalTexture<enum_Decal_DecalTexture>`. This is a convenience method, in most cases you should access the texture directly.

For example, instead of ``$Decal.set_texture(Decal.TEXTURE_ALBEDO, albedo_tex)``, use ``$Decal.texture_albedo = albedo_tex``.

One case where this is better than accessing the texture directly is when you want to copy one Decal's textures to another. For example:


.. tabs::

 .. code-tab:: gdscript

    for i in Decal.TEXTURE_MAX:
        $NewDecal.set_texture(i, $OldDecal.get_texture(i))

 .. code-tab:: csharp

    for (int i = 0; i < (int)Decal.DecalTexture.Max; i++)
    {
        GetNode<Decal>("NewDecal").SetTexture(i, GetNode<Decal>("OldDecal").GetTexture(i));
    }



.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
.. |constructor| replace:: :abbr:`constructor (This method is used to construct a type.)`
.. |static| replace:: :abbr:`static (This method doesn't need an instance to be called, so it can be called directly using the class name.)`
.. |operator| replace:: :abbr:`operator (This method describes a valid operator to use with this type as left-hand operand.)`
